---
title: Distribueringsriktlinjer för kontrollenhetens integreringsexempel för Sverige (äldre)
description: Denna artikel innehåller riktlinjer för distribution av exempel på kontrollenhetsintegrering för Sverige från Retail SDK
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: fcc35a2203641b24fe4edd2ab34f2e4d5db9bb53
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324308"
---
# <a name="deployment-guidelines-for-the-control-unit-integration-sample-for-sweden-legacy"></a>Distribueringsriktlinjer för kontrollenhetens integreringsexempel för Sverige (äldre)

[!include [banner](../includes/banner.md)]

Denna artikel ger riktlinjer för distribution av integreringsexempel för kontrollenhet för Sverige från utvecklingspaketet för detaljhandelsprogramvara (SDK) på en virtuell dator för utvecklare i Microsoft Dynamics Lifecycle Services (LCS). Mer information om exemplet på räkenskapsintegrering finns i [Exempel på integrering av kontrollenhet för Sverige](emea-swe-fi-sample.md). 

Exemplet på skatteintegrering för Sverige ingår i Retail SDK. Information om hur du installerar och använder SDK finns i [Retail programutvecklingskit (SDK) arkitektur](../dev-itpro/retail-sdk/retail-sdk-overview.md). Det här exemplet består av tillägg för Commerce Runtime (CRT), Hardware Station och kassa. Om du vill köra det här exemplet måste du ändra och bygga CRT, Hardware Station- och kassaprojekt. Vi rekommenderar att du använder en icke-modifierad detaljhandels-SDK för att utföra de ändringar som beskrivs i denna artikel. Vi rekommenderar också att du använder ett källkontrollsystem, till exempel Azure DevOps, där inga filer har ändrats ännu.

## <a name="development-environment"></a>Utvecklingsmiljö

Följ dessa steg för att konfigurera en utvecklingsmiljö så att du kan testa och utöka exemplet.

### <a name="enable-crt-extensions"></a>Aktivera CRT-tillägg

CRT tilläggskomponenter inkluderas i CRT-exemplen. För att slutföra följande procedurer, öppna **CommerceRuntimeSamples.sln** lösningen under **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentprovidercleancashsample-component"></a>DocumentProvider. CleanCashSample-komponent

1. Leta upp projektet **Runtime.Extensions.DocumentProvider.CleanCashSample** och skapa det.
2. I mappen **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Commerce Scale Unit:** kopiera filen till mappen **\\bin\\ext** under Internet Information Services (IIS) Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera filen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    ```

#### <a name="extension-configuration-file"></a>Tilläggskonfigurationsfil

1. Hitta konfigurationsfilen för tillägget för CRT:

    - **Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

2. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

### <a name="enable-hardware-station-extensions"></a>Aktivera tilläggen för Hardware Station

Tilläggskomponenterna för Hardware Station ingår i Hardware Station exemplen. För att slutföra följande procedurer, öppna lösningen **HardwareStationSamples.sln**, under **RetailSdk\\SampleExtensions\\HardwareStation**.

#### <a name="cleancash-component"></a>CleanCash-komponent

1. Leta upp projektet **HardwareStation.Extension.CleanCashSample** och skapa det.
2. I mappen **Extension.CleanCashSample\\bin\\Debug** hitta **Contoso.Commerce.HardwareStation.CleanCashSample.dll** och sammansättningsfilen **Interop.CleanCash\_1\_1.dll**.
3. Kopiera sammansättningsfilerna till Hardware Station-tilläggsmappen:

    - **Delad Hardware Station** : kopiera filerna till **binge**-mappen under IIS Hardware Station webbplatsen.
    - **Dedikerad Hardware Station på Modern POS** : kopiera filerna till platsen för Modern POS Client Broker.

4. Leta reda på tilläggskonfigurationsfilen för Hardware Station-tillägg. Filen heter **HardwareStation.Extension.config**.

    - **Delad Hardware Station** : filen är under IIS Hardware Station webbplatsen.
    - **Dedikerad Hardware Station på Modern POS** : filen är under platsen för Modern POS Client Broker.

5. Lägg till följande rad i avsnittet **sammansättning** i konfigurationsfilen.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

### <a name="enable-modern-pos-extension-components"></a>Aktivera tilläggskomponenter för Modern POS

1. Öppna lösningen **ModernPOS.sln** under **RetailSdk\\POS** och se till att den kan kompileras utan fel. Kontrollera dessutom att du kan köra Modern POS från Visual Studio med hjälp av kommandot **kör**.

    > [!NOTE]
    > Modern POS får inte anpassas. Du måste aktivera User Account Control (UAC) och du måste avinstallera tidigare installerade instanser av Modern POS efter behov.

2. Aktivera tilläggen som måste läsas in genom att lägga till följande rader i filen **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
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
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > Mer information och exempel som visar hur du inkluderar källkodsmappar och aktiverar tillägg som ska läsas in finns i instruktionerna i readme.md filen i projektet **Pos.Extensions**.

3. Återskapa lösningen.
4. Kör lösningen med hjälp av kommandot **kör** och följa stegen i handboken Retail SDK.

## <a name="production-environment"></a>Produktionsmiljö

Föregående procedur aktiverar tilläggen som är komponenter i exemplet på integrering av styrenhet. Förutom att du måste följa dessa steg för att skapa distribuerbara paket som innehåller Commerce-komponenter och för att tillämpa dessa paket i en produktionsmiljö.

1. Gör följande ändringar i paketkonfigurationsfilerna under mappen **RetailSdk\\Assets**:

    - I konfigurationsfilerna **commerceruntime.ext.config** och **CommerceRuntime.MPOSOffline.Ext.config** lägger du till följande rader i avsnittet **komposition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
        ```

    - I konfigurationsfilen **HardwareStation.Extension.config** lägg till följande rad i avsnittet **komposition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
        ```

2. Gör följande ändringar i konfigurationsfilerna för paketanpassning **Customization.settings** under **BuildTools**:

    - Lägg till följande rader om du vill inkludera CRT-tilläggen i de distribuerbara paketen.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
        ```

    - Lägg till följande rad om du vill inkludera Hardware Station-tillägget i de distribuerbara paketen.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

3. Aktivera kassatillägget genom att lägga till följande rader i filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
            "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

4. Starta MSBuild-Kommandotolken för Visual Studio-verktyget och **kör MSBuild** under mappen Retail SDK för att skapa distribuerbara paket.
5. Tillämpa paketen via LCS eller manuellt. Mer information finns i [skapa distribuerbara paket](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
6. Slutföra alla inställningsuppgifter som beskrivs i avsnittet [konfigurera integreringen med kontrollenheter](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).

## <a name="design-of-the-extensions"></a>Design av tilläggen

### <a name="crt-extension-design"></a>CRT tilläggsdesign

Syftet med tillägget som är en skattedokument leverantör är att generera tjänstspecifika dokument och hantera svar från kontrollenheten.

CRT-tillägget är **Runtime.Extensions.DocumentProvider.CleanCashSample**.

Mer information om design av lösningen av räkenskapsintegrering finns i [Process för räkenskapsregistrering och exempel på räkenskapsintegrering för kvittoskrivarenheter och tjänster](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Begärandehanterare

Det finns en enda **DocumentProviderCleanCash**-begärandehanterare för dokumentprovidern. Den här hanteraren används för att generera skattedokument för kontrollenheten.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Commerce headquarters.

Kopplingen stöder följande begäranden:

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett tjänstspecifikt dokument som ska registreras i kontrollenheten.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på. För närvarande stöds försäljningshändelser och granskningshändelser.

#### <a name="configuration"></a>Inställningar

Konfigurationsfilen **DocumentProviderFiscalCleanCashSample** finns i mappen **konfiguration** för tilläggsprojektet. Syftet med den här filen är att aktivera inställningar för dokumentprovidern som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering. Följande inställningar är tillagda:

- Mappning av momskoder

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget som är en räkenskapskoppling är att kommunicera med kontrollenheten.

Hardware Station-tillägget **HardwareStation.Extension.CleanCashSample**. Den använder HTTP-protokollet för att skicka dokument som CRT-tillägget genererar till kontrollenheten. Den hanterar också svar som tas emot från kontrollenheten.

#### <a name="request-handler"></a>Begärandehanterare

**CleanCashHandler** begäranhanteraren är startpunkten för hantering av begäranden till kontrollenheten.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Commerce headquarters.

Kopplingen stöder följande begäranden:

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till kontrollenheten och returnerar ett svar från den.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av kontrollenheten.
- **InitializeFiscalDeviceRequest** – den här begäran används för initiera kontrollenheten.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen finns i mappen **konfiguration** för tilläggsprojektet. Syftet med filen är att aktivera inställningar för räkenskapskoppling som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering. Följande inställningar är tillagda:

- **Anslutningssträng** – inställningarna för kontrollenhetens anslutning.
- **Tidsgräns** – hur länge, i millisekunder, som drivrutinen väntar på ett svar från kontrollenheten.

## <a name="migrating-from-the-earlier-integration-sample"></a>Migrera från det tidigare integreringsprovet

Om du använder det tidigare [exemplet för POS-integrering med styrenheter för Sverige](retail-sdk-control-unit-sample.md), kan du behöva migrera från den till det aktuella integreringsexemplet. För att kunna utnyttja förändringen och få snabba uppdateringar av funktionerna för Sverige i framtiden kan du behöva uppgradera, göra mindre kod- och konfigurationsjusteringar i tilläggen som du har skapat och återskapa dina lösningar. Inga större ändringar krävs i den tilläggslogik som du skapade. Det tidigare integreringsprovet och anpassningarna kommer att fortsätta att fungera om inga ändringar görs från din sida. Därför kan du planera, förbereda för och göra upptaget för din miljö.

### <a name="migration-process"></a>Migreringsprocess

Migreringen från det tidigare integreringsprovet till det aktuella styrenhetens integreringsprov bör baseras på konceptet med en gradvis uppdatering. Med andra ord bör alla Commerce headquarters och Commerce Scale Unit-komponenter redan uppdateras innan du börjar uppdatera POS och komponenter för Hardware Station.

För att förhindra en situation där en händelse eller transaktion undertecknas två gånger (det vill säga den är undertecknad av både den tidigare tillägget och den nuvarande tillägget), eller där en hämdelse eller transaktion inte kan undertecknas på grund av den saknade konfigurationen, rekommenderar vi att du stänger av alla POS- och Hardware Station-enheter som använder det tidigare exemplet och uppdaterar dem samtidigt. Den här samtidiga uppdateringen kan göras, till exempel i butik för butik genom att uppdatera butikens funktionsprofil och Hardware Station maskinvaruprofil.

Migreringsprocessen bör bestå av följande steg.

1. Uppdatera Commerce headquarters komponenterna.
1. Uppdatera Commerce Scale Unit-komponenterna och aktivera tilläggen för det aktuella exemplet.
1. Kontrollera att alla offlinetransaktioner synkroniseras från MPOS-enheter som har aktiverats offline.
1. Stäng av alla enheter som använder komponenterna i det tidigare exemplet.
1. Slutföra alla inställningsuppgifter som beskrivs i avsnittet [konfigurera integreringen med kontrollenheter](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).
1. Uppdatera komponenterna för POS och Hardware Station, inaktivera tilläggen som är delar av det tidigare exemplet och aktivera tilläggen för det aktuella exemplet.

    > [!NOTE]
    > Beroende på typ av miljö kan du hitta mer tekniska detaljer om migreringsprocessen i antingen avsnittet [Migrering i en utvecklingsmiljö](#migration-in-a-development-environment) eller avsnittet [Migrering i en produktionsmiljö](#migration-in-a-production-environment) i denna artikel.

### <a name="migration-in-a-development-environment"></a>Migrering i en utvecklingsmiljö

#### <a name="update-crt"></a>Uppdatera CRT

1. Leta upp projektet **Runtime.Extensions.DocumentProvider.CleanCashSample** och skapa det.
2. I mappen **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Commerce Scale Unit:** kopiera filen till mappen **\\bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera filen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Commerce Scale Unit:** Filen kallas **CommerceRuntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** Filen heter **CommerceRuntime.MPOSOffline.Ext.config** och den är i mappar **bin\\ext** under den lokala platsen för CRT-klienten Broker.

    > [!WARNING]
    > Redigera **inte** filerna CommerceRuntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

5. Hitta och ta bort det tidigare CRT-tillägget från konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Slutför inte det här steget förrän du uppdaterar alla kassaenheter som fungerar med den här CRT-instansen.

6. Registrera de aktuella exempel CRT-tilläggen i konfigurationsfilen för tillägget genom att lägga till följande rader.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

#### <a name="update-hardware-station"></a>Uppdatera Hardware Station

1. Leta upp projektet **HardwareStation.Extension.CleanCashSample** och skapa det.
2. I mappen **Extension.CleanCashSample\\bin\\Debug** hitta **Contoso.Commerce.HardwareStation.CleanCashSample.dll** och sammansättningsfilen **Interop.CleanCash\_1\_1.dll**.
3. Kopiera sammansättningsfilerna till Hardware Station-tilläggsmappen:

    - **Delad Hardware Station** : kopiera filerna till **binge**-mappen under IIS Hardware Station webbplatsen.
    - **Dedikerad Hardware Station på Modern POS** : kopiera filerna till platsen för Modern POS Client Broker.

4. Hitta **HardwareStation.Extension.config** tilläggskonfigurationsfilen:

    - **Fjärrstyrd Hardware Station** : filen är under IIS Hardware Station webbplatsen.
    - **Lokal Hardware Station på Modern POS** : filen är under platsen för Modern POS Client Broker.

    > [!WARNING]
    > Redigera **inte** filerna CommerceRuntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

5. Hitta och ta bort det tidigare Hardware Station-tillägget från konfigurationsfilen för tillägget.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 och tidigare](#tab/retail-7-3)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 och senare](#tab/retail-7-3-1)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 och senare](#tab/retail-10-0)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

6. Lägg till följande rad i avsnittet **sammansättning** i tilläggets konfigurationsfil.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

#### <a name="update-modern-pos"></a>Uppdatera Modern POS

1. Öppna lösningen **CloudPOS.sln** under **RetailSdk\\POS**.
2. Inaktivera det tidigare kassatillägget genom att ta bort följande rader filen **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Aktivera det aktuella tillägget för kassatillägget genom att lägga till följande rader i filen **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Uppdatera Cloud POS

1. Öppna lösningen **ModernPOS.sln** under **RetailSdk\\POS**.
2. Inaktivera det tidigare kassatillägget genom att ta bort följande rader filen **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Aktivera det aktuella tillägget för kassatillägget genom att lägga till följande rader i filen **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

### <a name="migration-in-a-production-environment"></a>Migrering i en produktionsmiljö

#### <a name="update-crt"></a>Uppdatera CRT

1. Ta bort tidigare CRT-tillägg från konfigurationsfilerna **CommerceRuntime.ext.config** och **CommerceRuntime.MPOSOffline.Ext.config** under mappen **RetailSdk\\Assets**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Slutför inte det här steget förrän du uppdaterar alla kassaenheter som fungerar med den här CRT-instansen.

2. Aktivera det aktuella exempel CRT-tillägg genom att göra följande ändringar i **CommerceRuntime.ext.config** och **CommerceRuntime.MPOSOffline.Ext.config** konfigurationsfilerna under mappen **RetailSdk\\Assets**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

3. I konfigurationsfilen för paketanpassning **Customization.settings** under mappen **BuildTools** lägger du till följande rader för att inkludera det aktuella exempletillägget CRT i i distribuerbara paket.

    ``` xml
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
    ```

#### <a name="update-hardware-station"></a>Uppdatera Hardware Station

1. Ta bort det tidigare Hardware Station-tillägget genom att modifiera konfigurationsfilen **HardwareStation.Extension.config**.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 och tidigare](#tab/retail-7-3)

    Ta bort följande avsnitt från konfigurationsfiler **HardwareStation.Shared.config** och **HardwareStation.Dedicated.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 och senare](#tab/retail-7-3-1)

    Ta bort följande avsnitt från konfigurationsfilen **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 och senare](#tab/retail-10-0)

    Ta bort följande avsnitt från konfigurationsfilen **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

2. Aktivera det aktuella exemplet på Hardware Station-tillägget genom att lägga till följande rad i avsnittet **komposition** i konfigurationsfil **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

3. Gör följande ändringar i konfigurationsfilerna för paketanpassning **Customization.settings** under **BuildTools**:

    - Ta bort följande rader för att utesluta den tidigare Hardware Station-tillägget från distribuerbara paket.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample.dll" />
        ```

    - Lägg till följande rad om du vill inkludera det aktuella exemplet Hardware Station-tillägget i de distribuerbara paketen.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

#### <a name="update-modern-pos"></a>Uppdatera Modern POS

1. Öppna lösningen **CloudPOS.sln** på **RetailSdk\\POS**.
2. Inaktivera det tidigare kassatillägget:

    - I filen **tsconfig.json**, lägg till mappen **FiscalRegisterSample** i undantagslistan.
    - Ta bort de tidigare raderna från filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Aktivera det aktuella exemplet för kassatillägget genom att lägga till följande rader i filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Uppdatera Cloud POS

1. Öppna lösningen **ModernPOS.sln** under **RetailSdk\\POS**.
2. Inaktivera det tidigare kassatillägget:

    - I filen **tsconfig.json**, lägg till mappen **FiscalRegisterSample** i undantagslistan.
    - Ta bort de tidigare raderna från filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Aktivera det aktuella exemplet för kassatillägget genom att lägga till följande rader i filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="create-deployable-packages"></a>Skapa driftfärdiga paket

Kör **msbuild** för hela Retail SDK för att skapa distribuerbara paket. Tillämpa paketen via LCS eller manuellt. Mer information finns i [Retail SDK-paket](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
