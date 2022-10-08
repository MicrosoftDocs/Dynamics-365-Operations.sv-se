---
title: Exempel på integrering av styrenhet för Sverige
description: I denna artikel finns en översikt över exemplet på räkenskapsintegrering för Sverige i Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-08
ms.openlocfilehash: 966ba3fab780991736f0c84d7eb68356c28a4022
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631273"
---
# <a name="control-unit-integration-sample-for-sweden"></a>Exempel på integrering av styrenhet för Sverige

[!include [banner](../includes/banner.md)]

I denna artikel finns en översikt över exemplet på räkenskapsintegrering för Sverige i Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Den här exempelfunktionen räkenskapsintegrering ersätter det tidigare [exemplet för POS-integrering med styrenheter för Sverige](retail-sdk-control-unit-sample.md). Det tidigare exemplet utnyttjar inte [ramverket för räkenskapsintegrering](./fiscal-integration-for-retail-channel.md) och blir föråldrat i senare uppdateringar. För information om hur du migrerar från det tidigare provet till det prov som motsvarar Dynamics 365 Commerce version **10.0.22 och tidigare**, se [Migrera från det tidigare integreringsprovet](emea-swe-fi-sample-sdk.md#migrating-from-the-earlier-integration-sample).

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
    - Senarelägg skatteregistrering.
    - Hoppa över räkenskapsregistrering eller markera transaktionen som registrerad och inkludera informationskoder för att fånga orsaken till felet och ytterligare information.
    - Kontrollera tillgängligheten för kontrollenheten innan en ny försäljningstransaktion öppnas eller en försäljningstransaktion slutförs.

### <a name="limitations-of-the-sample"></a>Begränsningar i provet

Styrenhetens integreringsprov för Sverige stöder för närvarande inte orderscenarier.

## <a name="setting-up-the-integration-with-control-units"></a>Ställa in integreringen med styrenheter

Mer information om de inställningar som krävs för Sverige finns i [konfigurera Commerce för Sverige](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden).

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

> [!NOTE]
> Det är viktigt att du anger rätt anpassade fältnamn, så som listas i registret ovan. Om fel anpassat fältnamn saknas data i kvittona.

#### <a name="configure-receipt-formats"></a>Konfigurera kvittoformat

För varje kvittoformat som krävs, ändra värdet för fältet **Utskriftssätt** till **Skriv alltid ut**.

I Layoutdesigner för kvitto, lägg till följande anpassade fält i avsnittet **Sidfot**. Observera att fältnamn motsvarar de språktexter som du definierade i föregående avsnitt i denna artikel.

- **Registrera kontrollkod** – det här fältet skriver ut kontrollkoden.
- **Registrera enhet** – i det här fältet skrivs kontrollenhetens tillverkningsnummer ut.

Mer information om hur du arbetar med kvittoformat finns i [Kvittomallar och utskrift](../receipt-templates-printing.md).

### <a name="set-up-fiscal-integration-for-sweden"></a>Ställ in räkenskapsintegrering för Sverige

Exemplet på integrering av kontrollenheten för Sverige baseras på [räkenskapsintegreringsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\CleanCash** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (till exempel [i version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). Proven [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) av en leverantör av skattedokument, vilket är ett tillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [konfigurera ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md).

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare (VM) i Microsoft Dynamics Lifecycle Services (LCS). Mer information finns i [Implementeringsriktlinjer för det kontrollenheten skrivarintegreringsexemplet för Sverige (äldre)](emea-swe-fi-sample-sdk.md).
>
> Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

Slutför konfigurationsstegen för räkenskapsintegrering som beskrivs i [konfigurera räkenskapsintegrering för Commerce-kanaler](setting-up-fiscal-integration-for-retail-channel.md).

1. [Ställa in process för räkenskapsregistrering](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Var noga med att notera inställningarna för den process för räkenskapsregistrering som är [specifika för det här kontrollenhetens integrering av prov](#set-up-the-registration-process).
1. [Ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Aktivera manuell körning av periodiserade skatteregistreringar](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).
1. [Konfigurera kanalkomponenter](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Ställa in registrationsprocessen

Om du vill aktivera registreringsprocessen, följ dessa steg för att konfigurera Commerce headquarters. Mer information om [Ställ in räkenskapsintegrering för handelskanaler](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Ladda ner konfigurationsfiler för providern av skattedokument och skatteanslutningen:

    1. Öppna [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen.
    1. Välj en korrekt version av frisläppningen enligt din SDK/programversion (till exempel **[frisläppning/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Öppna **src \> FiscalIntegration \> CleanCash**.
    1. Hämta konfigurationsfilen för räkenskapsdokumentprovidern på  **CommerceRuntime \> DocumentProvider.CleanCashSample \> Configuration \> DocumentProviderFiscalCleanCashSample.xml** (till exempel, [filen för version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/CommerceRuntime/DocumentProvider.CleanCashSample/Configuration/DocumentProviderFiscalCleanCashSample.xml)).
    1. Ladda ner konfigurationsfilen för räkenskapskoppling på **HardwareStation \> Connector.CleanCashSample \> Configuration \> ConnectorCleanCashSample.xml** (till exempel, [filen för version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/HardwareStation/Connector.CleanCashSample/Configuration/ConnectorCleanCashSample.xml)).

    > [!WARNING]
    > På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Konfigurationsfilerna för det här exemplet för skatteintegrering finns i följande mappar i Retail SDK på en utvecklar-VM i LCS:
    >
    > - **Konfigurationsfilen för räkenskapsdokumentprovidern:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml
    > - **Konfigurationsfil för räkenskapskoppling:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml
    > 
    > Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> delade Commerce-parametrar**. På fliken **allmänt** anger du alternativet **Aktivera räkenskapsintegrering** till **Ja**.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Leverantörer av skattedokument** och läs in konfigurationsfilen för skattedokumentprovidern som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Räkenskapskopplingar** och läs in konfigurationsfilen för räkenskapskoppling för skattedokumentprovidern som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Funktionsprofiler för koppling**. Skapa en ny funktionsprofil för anslutning. Välj dokumentprovidern och den koppling som du läst in tidigare. Uppdatera [datamappningsinställningarna](#default-data-mapping) efter behov.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Tekniska profiler för koppling**. Skapa en ny teknisk profil för koppling och välj räkenskapskoppling som du laddade tidigare. Uppdatera [kopplingsinställningarna](#fiscal-connector-settings) efter behov.
6. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Grupper för skattekoppling**. Skapa en ny grupp för räkenskapskoppling för den funktionsprofil för koppling som du skapade tidigare.
7. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Processer för räkenskapsregistrering**. Skapa en ny räkenskapsregistrering och räkenskapsregistrering och välj den grupp för räkenskapskoppling som du skapade tidigare.
8. Gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**. Välj en funktionsprofil som är kopplad till butiken där registreringsprocessen ska aktiveras. På snabbfliken **Process för räkenskapsregistrering**, välj räkenskapsregistreringsprocessen som du skapade tidigare.
9. Gåt ill **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Kassaprofiler \> Maskinvaruprofiler**. Välj en maskinvaruprofil som är länkad till den Hardware Station som kvittoskrivare ska anslutas till. På snabbfliken **Kringutrustning för räkenskaper**, välj teknisk profil för koppling som du skapade tidigare.
10. Öppna distributionstidsplanen (**Retail och Commerce \> Retail och Commerce-IT \> Distributionsschema**) och välj jobb **1070** och **1090** för att överföra data till kanaldatabasen.

#### <a name="default-data-mapping"></a>Standarddatamappning

Följande standarddatamappning ingår i konfigurationen av leverantören av skattedokument som tillhandahålls som en del av exemplet på räkenskapsintegrering.

- **Kodmappning för mervärdesskatt (VAT)** - Mappningen anger enhetsspecifika koder för mervärdesskatt (VAT) till motsvarande momskoder. Kodmappning av mervärdesskatt bör ha följande format:

    ```
    1 : code1 ; 2 : code2
    ```

    Här följer en förklaring av detta format:

    - *1* och *2* är enhetsspecifika momskoder.
    - Ett semikolon (;) används som avgränsare.
    - *kod1* och *kod2* är momskoder som har konfigurerat i Commerce headquarters. Du måste ändra exempelmappningen enligt momskoder som är konfigurerade i programmet.

    Styrenheter stöder upp till fyra olika momskoder. Därför kan momskodmappningen ställas in på det sätt som visas här:

    ```
    1 : code1 ; 2 : code2 ; 3 : code3 ; 4 : code4
    ```

    > [!NOTE]
    > Flera momskoder kan mappas till samma enhetsspecifika momskod.

#### <a name="fiscal-connector-settings"></a>Inställningar för räkenskapskoppling

Följande inställningar ingår i den skatteanslutningskonfiguration som tillhandahålls som en del av det skattemässiga integreringsexemplet:

- **Anslutningssträng** – inställningarna för kontrollenhetens anslutning.
- **Tidsgräns** – hur länge, i millisekunder, som drivrutinen väntar på ett svar från kontrollenheten.

### <a name="configure-channel-components"></a>Konfigurera kanalkomponenter

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Mer information finns i [Implementeringsriktlinjer för det kontrollenheten skrivarintegreringsexemplet för Sverige (äldre)](emea-swe-fi-sample-sdk.md).
>
> Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

#### <a name="set-up-the-development-environment"></a>Konfigurera en utvecklingsmiljö

Följ dessa steg för att konfigurera en utvecklingsmiljö för att testa och utöka provet.

1. Eller hämta [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions)-databasen. Välj en korrekt version av frisläppningen enligt din SDK/programversion. För mer information, se [Hämta Retail SDK-exempel och referenspaket från GitHub och NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Öppna kontrollenhet integreringslösningen **Dynamics365Commerce.Solutions\\FiscalIntegration\\CleanCash\\CleanCash.sln** och skapa den.
1. Installera CRT-tillägg:

    1. Sök efter CRT installationsprogram:

        - **Commerce Scale Unit:** I mappen **CleanCash\\ScaleUnit\\ScaleUnit.CleanCash.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **ScaleUnit.CleanCash.Installer**.
        - **Lokal CRT i Modern POS:** I mappen **CleanCash\\ModernPOS\\ModernPOS.CleanCash.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **ModernPOS.CleanCash.Installer**.

    2. Starta CRT installationsprogrammet för filnamnstillägget från kommandorad:

        - **Commerce Scale Unit.**

            ```Console
            ScaleUnit.CleanCash.Installer.exe install --verbosity 0
            ```

        - **Lokal CRT på Modern POS:**

            ```Console
            ModernPOS.CleanCash.Installer.exe install --verbosity 0
            ```

1. Install tilläggen för Hardware Station:

    1. I mappen **CleanCash\\HardwareStation\\HardwareStation.CleanCash.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **HardwareStation.CleanCash.Installer**.
    1. Starta installationsprogrammet för filnamnstillägget från kommandorad:

        ```Console
        HardwareStation.CleanCash.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Produktionsmiljö

Följ stegen i [Konfigurera en byggpipeline för ett skatteintegreringsprov](fiscal-integration-sample-build-pipeline.md) för att generera och släppa Cloud Scale Unit och självbetjäningsdistributionspaket för skatteintegreringsexemplet. Mall **CleanCash build-pipeline.yml** YAML-filen finns i **Pipeline\\YAML_Files** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-the-extensions"></a>Design av tilläggen

Exemplet på integrering av kontrollenheten för Sverige baseras på [räkenskapsintegreringsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\CleanCash** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (till exempel [i version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). Proven [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) av en leverantör av skattedokument, vilket är ett tillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [konfigurera ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md).

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Mer information finns i [Implementeringsriktlinjer för det kontrollenheten skrivarintegreringsexemplet för Sverige (äldre)](emea-swe-fi-sample-sdk.md). Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

### <a name="crt-extension-design"></a>CRT tilläggsdesign

Syftet med tillägget som är en skattedokument leverantör är att generera tjänstspecifika dokument och hantera svar från kontrollenheten.

#### <a name="request-handler"></a>Begärandehanterare

Det finns en enda **DocumentProviderCleanCash**-begärandehanterare för dokumentprovidern. Den här hanteraren används för att generera skattedokument för kontrollenheten.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Commerce headquarters.

Kopplingen stöder följande begäranden:

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett tjänstspecifikt dokument som ska registreras i kontrollenheten.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på. För närvarande stöds försäljningshändelser och granskningshändelser.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av skattedokument finns på **src\\FiscalIntegration\\CleanCash\\CommerceRuntime\\DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml** i databasen [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Syftet med den här filen är att aktivera inställningar för dokumentprovidern som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering.

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget som är en räkenskapskoppling är att kommunicera med kontrollenheten. Den använder HTTP-protokollet för att skicka dokument som CRT-tillägget genererar till kontrollenheten. Den hanterar också svar som tas emot från kontrollenheten.

#### <a name="request-handler"></a>Begärandehanterare

**CleanCashHandler** begäranhanteraren är startpunkten för hantering av begäranden till kontrollenheten.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Commerce headquarters.

Kopplingen stöder följande begäranden:

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till kontrollenheten och returnerar ett svar från den.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av kontrollenheten.
- **InitializeFiscalDeviceRequest** – den här begäran används för initiera kontrollenheten.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av anslutningsprogram på **src\\FiscalIntegration\\CleanCash\\HardwareStation\\Connector.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Syftet med filen är att aktivera inställningar för räkenskapskoppling som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
