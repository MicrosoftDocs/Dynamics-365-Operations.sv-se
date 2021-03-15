---
title: Exempel på integration av kontrollenhet för Sverige
description: I det här avsnittet finns en översikt över exemplet på räkenskapsintegration för Sverige.
author: sepism
manager: annbe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Sweden
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 30f9702a5002c9da8f125feb22d7d0bd08d0838d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985929"
---
# <a name="control-unit-integration-sample-for-sweden"></a>Exempel på integration av kontrollenhet för Sverige

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Den här exempelfunktionen räkenskapsintegrering ersätter det tidigare [exemplet för POS-integrering med styrenheter för Sverige](retail-sdk-control-unit-sample.md). Det tidigare exemplet utnyttjar inte [ramverket för räkenskapsintegration](./fiscal-integration-for-retail-channel.md) och blir föråldrat i senare uppdateringar. Information om hur du migrerar från det tidigare exemplet till det aktuella exemplet finns i avsnittet [migrera från det tidigare integrationsexemplet](#migrating-from-the-earlier-integration-sample).

## <a name="introduction"></a>Introduktion

Commerce-funktionen för Sverige inkluderar ett exempel för att integrera kassa med Sverige-specifika kvittoskrivarenhet som kallas *kontrollenheter*. Det här exemplet utökar [funktionen räkenskapsintegrering](fiscal-integration-for-retail-channel.md). Det antas att en enhet är fysiskt ansluten till maskinvarustationerna som POS är kopplad till. Som exempel använder det här exemplet programmeringsgränssnittet (API) för [Cleancash-typen A](https://www.retailinnovation.se/produkter)-styrenhet av Retail innovation HTT AB. Version 1.1.4 av CleanCash-API används.

Exemplet tillhandahålls i form av källkod och är en del av Retail Software Development Kit (SDK).

Microsoft släpper inte någon maskinvara, programvara eller dokumentation från Retail innovation HTT AB. För information om hur du får kontrollenheten och använder den, kontakta [Retail Innovation HTT AB](https://www.retailinnovation.se/).

## <a name="scenarios"></a>Scenarier

Kontrollenhetens integrering av prov för Sverige omfattar följande funktioner:

- Försäljning, returer och kvittokopior registreras automatiskt i en kontrollenhet som är ansluten till maskinvarustationen som är kopplad till POS.
- Kontrollkoden och tillverkningsnumret för kontrollenheten för en registrerad transaktion fångas in från kontrollenheten och sparas i transaktionen. Dessa data kallas också ett *räkenskapssvar*. Det skattemässiga svaret kan visas på sidan **butikstransaktioner**.
- Anpassade fält för kontrollkoden och tillverkningsnumret för kontrollenheten kan läggas till en kvittolayout. På så sätt kan du skriva ut räkenskapsårets svar för en transaktion på en inleverans.
- Räkenskapssvar för en transaktion visas på kanalrapporten **elektronisk journal (Sverige)**.
- Det finns flera alternativ för felhantering. Nedan följer några exempel:

    - Försök med räkenskapsregistrering om ett nytt försök är möjligt. Du kan försöka registrera räkenskapsregistrering om till exempel styrenheten inte är ansluten, inte är redo eller inte svarar.
    - Senarelägg räkenskapsregistrering.
    - Hoppa över räkenskapsregistrering eller markera transaktionen som registrerad och inkludera informationskoder för att fånga orsaken till felet och ytterligare information.
    - Kontrollera tillgängligheten för kontrollenheten innan en ny försäljningstransaktion öppnas eller en försäljningstransaktion slutförs.

### <a name="default-data-mapping"></a>Standarddatamappning

Följande standarddatamappning ingår i konfigurationen av leverantören av skattedokument som distribueras som en del av exemplet på räkenskapsintegration.

**Kodmappning för mervärdesskatt (VAT)** anger enhetsspecifika koder för mervärdesskatt (VAT) till motsvarande momskoder. Kodmappning av mervärdesskatt bör ha följande format:

*1 : kod1 ; 2 : kod2*

Här följer en förklaring av detta format:

- *1* och *2* är enhetsspecifika momskoder.
- Ett semikolon (;) används som avgränsare.
- *kod1* och *kod2* är momskoder som har konfigurerat i Administration.

Styrenheter stöder upp till fyra olika momskoder. Därför kan momskodmappningen ställas in på det sätt som visas här:

*1 : kod1 ; 2 : kod2 ; 3 : kod3 ; 4 : kod4*

> [!NOTE]
> Flera momskoder kan mappas till samma enhetsspecifika momskod.

### <a name="limitations-of-the-sample"></a>Begränsningar i provet

Styrenhetens integrationsprov för Sverige stöder för närvarande inte orderscenarier.

## <a name="setting-up-the-integration-with-control-units"></a>Ställa in integrationen med styrenheter

Mer information om de inställningar som krävs för Sverige finns i [ställa in Commerce för Sverige](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden).

### <a name="configuring-swedenspecific-receipts"></a>Konfigurera Sverige – specifika kvitton

#### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Konfigurera anpassade fält så att de kan användas i kvittoformat för försäljningskvitton

Du kan konfigurera språktext och anpassade fält som används i kassakvittoformat. Standardföretaget för den användare som skapar kvittoinställningen bör vara samma juridiska person där språktextinställningarna skapas. Du kan också skapa samma språktexter i både användarens standardföretag och den juridiska personen i butiken som installationen har skapats för.

På sidan **Språktext** kan du lägga till följande poster för etiketterna för de anpassade fälten för kvittolayout. Observera att värdena **Språk-ID**, **Text-ID** och **Text** som visas i tabellen bara är exempel. Du kan ändra dem för att uppfylla dina krav. Värdena för **text-ID** som du använder måste dock vara unika och de måste vara lika med eller större än 900001.

Lägg till följande kassaetiketter i avsnittet **kassa** på sidan **språktext**.

| Språk-ID | Text-ID | Text                  |
|-------------|---------|-----------------------|
| en-US       | 900001  | Registrera kontrollkod |
| en-US       | 900002  | Registrera enhet       |

På sidan **Anpassade fält** kan du lägga till följande poster för anpassade fält för kvittolayouter. Observera att värdena **Text-ID för rubrik** måste motsvara de värden för **Text-ID** som du angav på sidan **språktext**.

| Namn                         | Typ    | Text-ID för rubrik |
|------------------------------|---------|-----------------|
| SE_FISCALREGISTERCONTROLCODE | Inleverans | 900001          |
| SE_FISCALREGISTERID          | Inleverans | 900002          |

#### <a name="configure-receipt-formats"></a>Konfigurera kvittoformat

För varje kvittoformat som krävs, ändra värdet för fältet **Utskriftssätt** till **Skriv alltid ut**.

I Layoutdesigner för kvitto, lägg till följande anpassade fält i avsnittet **Sidfot**. Observera att fältnamn motsvarar de språktexter som du definierade i föregående avsnitt i det här avsnittet.

- **Registrera kontrollkod** – det här fältet skriver ut kontrollkoden.
- **Registrera enhet** – i det här fältet skrivs kontrollenhetens tillverkningsnummer ut.

Mer information om hur du arbetar med kvittoformat finns i [Kvittomallar och utskrift](../receipt-templates-printing.md).

### <a name="configure-fiscal-integration"></a>Konfigurera räkenskapsintegration

Slutför konfigurationsstegen för räkenskapsintegration som beskrivs i [ställa in räkenskapsintegration för Commerce-kanaler](setting-up-fiscal-integration-for-retail-channel.md):

- [Ställa in process för räkenskapsregistrering](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Var noga med att notera inställningarna för den process för räkenskapsregistrering som är [specifika för det här kontrollenhetens integrering av prov](#set-up-the-registration-process).
- [Ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
- [Aktivera manuell körning av uppskjutna räkenskapsregistreringar](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

## <a name="deployment-guidelines-for-cash-registers-for-sweden"></a>Riktlinjer för distribution av kassaapparater för Sverige

Det här avsnittet fungerar som en distributionsguide som visar hur du aktiverar lokalisering av Microsoft Dynamics 365 Commerce för Sverige. Lokaliseringen är en del av Retail SDK. Information om hur du installerar och använder Retail SDK finns i [dokumentation för Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Det här exemplet består av tillägg för Commerce Runtime (CRT), kassa och Hardware Station. Om du vill köra det här exemplet måste du ändra och bygga CRT och Hardware Station-projekt. Vi rekommenderar att du använder en icke-modifierad Retail SDK för att göra de ändringar som beskrivs i det här avsnittet. Vi rekommenderar också att du använder ett källkontrollsystem, till exempel Microsoft Azure DevOps, där inga filer har ändrats ännu.

Följ dessa steg för att konfigurera en utvecklingsmiljö så att du kan testa och utöka exemplet. Du måste också slutföra alla nödvändiga inställningsuppgifter som beskrivs i avsnittet [ställa in integrationen med kontrollenheter](#setting-up-the-integration-with-control-units).

### <a name="enable-crt-extensions"></a>Aktivera CRT-tillägg

CRT tilläggskomponenter inkluderas i CRT-exemplen. För att slutföra följande procedurer, öppna CRT-lösningen, **CommerceRuntimeSamples.sln**, under **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentprovidercleancashsample-component"></a>DocumentProvider. CleanCashSample-komponent

1. Leta upp projektet **Runtime.Extensions.DocumentProvider.CleanCashSample** och skapa det.
2. I mappen **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Commerce Scale Unit:** kopiera sammansättningen till mappen **\\bin\\ext** under Microsoft Internet Information Services (IIS) Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    ```

#### <a name="update-the-extension-configuration-file"></a>Uppdatera konfigurationsfilen för tillägget

1. Hitta konfigurationsfilen för tillägget för CRT:

    - **Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

2. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

### <a name="enable-hardware-station-extensions"></a>Aktivera tilläggen för Hardware Station

Tilläggskomponenterna för Hardware Station ingår i Hardware Station exemplen. För att slutföra följande procedurer, öppna lösningen **HardwareStationSamples.sln.sln**, under **RetailSdk\\SampleExtensions\\HardwareStation**.

#### <a name="cleancash-component"></a>CleanCash-komponent

1. Leta upp projektet **HardwareStation.Extension.CleanCashSample** och skapa det.
2. I mappen **Extension.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.HardwareStation.CleanCashSample.dll**.
3. Kopiera sammansättningsfilen till Hardware Station-tilläggsmappen:

    - **Delad Hardware Station** : kopiera filen till **binge**-mappen under IIS Hardware Station webbplatsen.
    - **Dedikerad Hardware Station på Modern POS** : kopiera filen till platsen för Modern POS Client Broker.

4. Leta reda på tilläggskonfigurationsfilen för Hardware Station-tillägg. Filen heter **HardwareStation.Extension.config**.

    - **Delad Hardware Station** : filen är under IIS Hardware Station webbplatsen.
    - **Dedikerad Hardware Station på Modern POS** : filen är under platsen för Modern POS Client Broker.

5. Lägg till följande rad i avsnittet **sammansättning** i konfigurationsfilen.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
    ```

### <a name="enable-modern-pos-extension-components"></a>Aktivera tilläggskomponenter för Modern POS

1. Öppna lösningen på **RetailSdk\\POS\\ModernPOS.sln** och se till att den kan kompileras utan fel. Kontrollera dessutom att du kan köra Modern POS från Microsoft Visual Studio med hjälp av kommandot **kör**.

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

1. Öppna lösningen på **RetailSdk\\POS\\CloudPOS.sln** och se till att den kan kompileras utan fel.
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

### <a name="set-up-the-registration-process"></a>Ställa in registrationsprocessen

Om du vill aktivera registreringsprocessen, följ dessa steg för att ställa in Administration. Mer information finns [Ställ in en räkenskapsregistreringsprocess](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Delade parametrar**. På fliken **allmänt** anger du alternativet **Aktivera räkenskapsintegration** till **Ja**.
2. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegration \> Räkenskapskopplingar** och läs in kopplingskonfigurationen. Filens plats är **RetailSdk\\SampleExtensions\\HardwareStation\\Extension.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml**.
3. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegration \> Leverantörer av skattedokument** och läs in konfigurationens dokumentleverantör. Filens plats är **RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml**.
4. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Funktionsprofiler för koppling**. Skapa en ny funktionsprofil för koppling och välj dokumentleverantören och kopplingen som du laddade tidigare. Uppdatera datamappningsinställningarna efter behov.
5. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Tekniska profiler för koppling**. Skapa en ny teknisk profil för koppling och välj kopplingen som du laddade tidigare. Uppdatera kopplingsinställningarna efter behov.
6. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Grupper för skattekoppling**. Skapa en ny grupp för räkenskapskoppling för den funktionsprofil för koppling som du skapade tidigare.
7. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Processer för räkenskapsregistrering**. Skapa en ny räkenskapsregistrering, skapa ett steg för räkenskapsregistrering och välj den grupp för räkenskapskoppling som du skapade tidigare.
8. Gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**. Välj en funktionsprofil som är kopplad till butiken där registreringsprocessen ska aktiveras. På snabbfliken **Process för räkenskapsregistrering**, välj räkenskapsregistreringsprocessen som du skapade tidigare.
9. Gåt ill **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Kassaprofiler \> Maskinvaruprofiler**. Välj en maskinvaruprofil som är länkad till den Hardware Station som styrenheten ska anslutas till. På snabbfliken **Kringutrustning för räkenskaper**, välj teknisk profil för koppling som du skapade tidigare.
10. Öppna distributionstidsplanen (**Retail och Commerce \> Retail och Commerce-IT \> Distributionsschema**) och välj jobb **1070** och **1090** för att överföra data till kanaldatabasen.

### <a name="production-environment"></a>Produktionsmiljö

Föregående procedur aktiverar tilläggen som är komponenter i exemplet på skatteregistreringstjänsten. Förutom att slutföra proceduren måste du följa dessa steg för att skapa distribuerbara paket som innehåller Commerce-komponenter och för att tillämpa dessa paket i en produktionsmiljö.

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
5. Tillämpa paketen via Microsoft Dynamics Lifecycle Services (LCS) eller manuellt. Mer information finns i [skapa distribuerbara paket](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-the-extensions"></a>Design av tilläggen

### <a name="crt-extension-design"></a>CRT tilläggsdesign

Syftet med tillägget som är en skattedokument leverantör är att generera tjänstspecifika dokument och hantera svar från räkenskapsregistreringstjänsten.

CRT-tillägget är **Runtime.Extensions.DocumentProvider.CleanCashSample**.

Mer information om design av lösningen av räkenskapsintegration finns i [Process för räkenskapsregistrering och exempel på räkenskapsintegration för kvittoskrivarenheter](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

#### <a name="request-handler"></a>Begärandehanterare
    
Det finns en enda **DocumentProviderCleanCash**-begärandehanterare för dokumentprovidern. Den här hanteraren används för att generera skattedokument för räkenskapsregistreringstjänst.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Administration.

Kopplingen stöder följande begäranden:

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett tjänstspecifikt dokument som ska registreras i räkenskapsregistreringstjänst.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på. För närvarande stöds försäljningshändelser och granskningshändelser.

#### <a name="configuration"></a>Inställningar

Konfigurationsfilen **DocumentProviderFiscalCleanCashSample** finns i mappen **konfiguration** för tilläggsprojektet. Syftet med den här filen är att aktivera inställningar för dokumentprovidern som ska konfigureras från Administration. Filformatet justeras med kraven för konfiguration av räkenskapsintegration. Följande inställningar är tillagda:

- Mappning av momskoder

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget som är en räkenskapskoppling är att kommunicera med räkenskapsregistreringstjänsten.

Hardware Station-tillägget **HardwareStation.Extension.CleanCashSample**. Den använder HTTP-protokollet för att skicka dokument som CRT-tillägget genererar till räkenskapsregistreringstjänsten. Den hanterar också svar som tas emot från räkenskapsregistreringstjänsten.

#### <a name="request-handler"></a>Begärandehanterare

**Cleancashhandler** begäranhanteraren är startpunkten för hantering av begäranden till räkenskapsregistreringstjänst.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Administration.

Kopplingen stöder följande begäranden:

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till räkenskapsregistreringstjänsten och returnerar ett svar från den.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av tjänsten för räkenskapsregistrering.
- **InitializeFiscalDeviceRequest** – den här begäran används för initiera tjänsten för räkenskapsregistrering.

#### <a name="configuration"></a>Inställningar

Konfigurationsfilen finns i mappen **konfiguration** för tilläggsprojektet. Syftet med filen är att aktivera inställningar för räkenskapskoppling som ska konfigureras från Administration. Filformatet justeras med kraven för konfiguration av räkenskapsintegration. Följande inställningar är tillagda:

- **Anslutningssträng** – inställningarna för kontrollenhetens anslutning.
- **Tidsgräns** – hur länge, i millisekunder, som drivrutinen väntar på ett svar från räkenskapsregistreringstjänst.

## <a name="migrating-from-the-earlier-integration-sample"></a>Migrera från det tidigare integrationsprovet

Om du använder det tidigare [exemplet för POS-integrering med styrenheter för Sverige](retail-sdk-control-unit-sample.md), kan du behöva migrera från den till det aktuella integrationsexemplet. För att kunna utnyttja förändringen och få snabba uppdateringar av funktionerna för Sverige i framtiden kan du behöva uppgradera, göra mindre kod- och konfigurationsjusteringar i tilläggen som du har skapat och återskapa dina lösningar. Inga större ändringar krävs i den tilläggslogik som du skapade. Det tidigare integrationsprovet och anpassningarna kommer att fortsätta att fungera om inga ändringar görs från din sida. Därför kan du planera, förbereda för och göra upptaget för din miljö.

### <a name="migration-process"></a>Migreringsprocess

Migreringen från det tidigare integrationsprovet till det aktuella styrenhetens integrationsprov bör baseras på konceptet med en gradvis uppdatering. Med andra ord bör alla Administration och Commerce Scale Unit-komponenter redan uppdateras innan du börjar uppdatera POS och komponenter för Hardware Station.

För att förhindra en situation där en händelse eller transaktion undertecknas två gånger (det vill säga den är undertecknad av både den tidigare tillägget och den nuvarande tillägget), eller där den inte kan undertecknas på grund av den saknade konfigurationen, rekommenderar vi att du stänger av alla POS- och Hardware Station-enheter som använder det tidigare exemplet och uppdaterar dem samtidigt. Den här samtidiga uppdateringen kan göras, till exempel i butik för butik genom att uppdatera butikens funktionsprofil och Hardware Station maskinvaruprofil.

Migreringsprocessen bör bestå av följande steg.

1. Uppdatera Administration-komponenterna.
1. Uppdatera Commerce Scale Unit-komponenterna och aktivera tilläggen för det aktuella exemplet.
1. Kontrollera att alla offlinetransaktioner synkroniseras från MPOS-enheter som har aktiverats offline.
1. Stäng av alla enheter som använder komponenterna i det tidigare exemplet.
1. Slutföra alla inställningsuppgifter som beskrivs i avsnittet [ställa in integrationen med kontrollenheter](#setting-up-the-integration-with-control-units).
1. Uppdatera komponenterna för POS och Hardware Station, inaktivera tilläggen som är delar av det tidigare exemplet och aktivera tilläggen för det aktuella exemplet.

    > [!NOTE]
    > Beroende på typ av miljö kan du hitta mer tekniska detaljer om migreringsprocessen i antingen avsnittet [Migration i en utvecklingsmiljö](#migration-in-a-development-environment) avsnittet [Migration i en produktionsmiljö](#migration-in-a-production-environment).

### <a name="migration-in-a-development-environment"></a>Migrering i en utvecklingsmiljö

#### <a name="update-crt"></a>Uppdatera CRT

1. Leta upp projektet **Runtime.Extensions.DocumentProvider.CleanCashSample** och skapa det.
2. I mappen **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Commerce Scale Unit:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

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
2. I mappen **Extension.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.HardwareStation.CleanCashSample.dll**.
3. Kopiera sammansättningsfilen till Hardware Station-tilläggsmappen:

    - **Delad Hardware Station** : kopiera filen till **binge**-mappen under IIS Hardware Station webbplatsen.
    - **Dedikerad Hardware Station på Modern POS** : kopiera filen till platsen för Modern POS Client Broker.

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
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
    ```

#### <a name="update-modern-pos"></a>Uppdatera Modern POS

1. Öppna lösningen på **RetailSdk\\POS\\CloudPOS.sln**.
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

1. Öppna lösningen på **RetailSdk\\POS\\ModernPOS.sln**.
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

3. I konfigurationsfilen för paketanpassning **Customization.settings** under mappen **BuildTools** lägger du till följande rader för att inkludera det aktuella exempeltillägget CRT i i distribuerbara paket.

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
        <ISV_CommerceRuntime_CustomizableFileInclude="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample.dll" />
        ```

    - Lägg till följande rad om du vill inkludera det aktuella exemplet Hardware Station-tillägget i de distribuerbara paketen.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        ```

#### <a name="update-modern-pos"></a>Uppdatera Modern POS

1. Öppna lösningen på **RetailSdk\\POS\\CloudPOS.sln**.
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

1. Öppna lösningen på **RetailSdk\\POS\\ModernPOS.sln**.
2. Inaktivera det tidigare kassatillägget:

    - I filen **tsconfig.json**, lägg till mappen **FiscalRegisterSample** i undantagslistan.
    - Ta bort de tidigare raderna från filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

4. Aktivera det aktuella exemplet för kassatillägget genom att lägga till följande rader i filen **extensions.json** under mappen **RetailSDK\\POS\\Extensions**.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]