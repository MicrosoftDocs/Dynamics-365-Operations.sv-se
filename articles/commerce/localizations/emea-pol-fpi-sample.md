---
title: Exempel på integrering av kvittoskrivare för Polen
description: I det här avsnittet finns en översikt över exemplet på räkenskapsintegration för Polen i Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-2-1
ms.openlocfilehash: 1b3d7d59494b215ae47f710e200e7e0c57e4ca29
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944875"
---
# <a name="fiscal-printer-integration-sample-for-poland"></a>Exempel på integrering av kvittoskrivare för Polen

[!include[banner](../includes/banner.md)]

I det här avsnittet finns en översikt över exemplet på räkenskapsintegration för Polen i Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce-funktionen för Polen omfattar en exempelintegration av kassan (POS) med en kvittoskrivare. Exemplet utökar funktionen för [skatteintegration](fiscal-integration-for-retail-channel.md) och stöder POSNET THERMAL HD 2.02 protokollet för kvittoskrivare från [Posnet Polska S.A.](https://www.posnet.com.pl) Exemplet möjliggör kommunikation med en kvittoskrivare som är ansluten via en COM-port med hjälp av en inbyggd programvarudrivrutin. Den implementerades och testades med hjälp av en mjukvaruemulator som Posnet tillhandahållit för Posnet Thermal HD FV EJ kvittoskrivare. Exemplet tillhandahålls i form av källkod och är en del av Retail Software Development Kit (SDK).

Microsoft släpper inte någon maskinvara, programvara eller dokumentation från Posnet. Om du vill ha information om hur du får kvittoskrivaren och använder den kan du kontakta [Posnet Polska S.A.](https://www.posnet.com.pl)

## <a name="scenarios"></a>Scenarier

Följande scenarier täcks av integrationsexempel för kvittoskrivare för Polen:

- Försäljningsscenarier:

    - Skriv ut ett skatteinleverans för kontantbetalningsförsäljning och hämtköp och returer.
    - Hämta ett svar från kvittoskrivaren och lagra det i kanaldatabasen.
    - Skatter:

        - Mappa till kvittoskrivarens momskoder (avdelningar).
        - Överför mappade skattedata till kvittoskrivaren.

    - Betalningar.

        - Mappa till kvittoskrivarens betalningsmetoder.
        - Skriv ut betalning på en skatteinleverans.
        - Skriv ut ändringsinformation.

    - Skriv ut radrabatter.
    - Presentkort:

        - Uteslut en utfärdad/omdebiterad presentkortsrad från ett skattekvitto för en försäljning.
        - Skriv ut en betalning där ett presentkort används som vanlig betalningsmetod.

    - Skriv ut räkenskapskvitton för operationer inom kundorder:

        - Ett skattekvitto skrivs inte ut för en kundorderdeposition.
        - Skriv ut en skattekvitto för leveransrader i en kundorder.
        - Skriv ut ett skattekvitto för upphämtningen av en kundorder.
        - Skriv ut en skatteinleverans för en returorder.

    - Skriv ut [kundinformation](emea-pol-customer-information.md) som har angetts för en försäljningstransaktion på en skatteinleverans. Ett exempel på denna information är kundens momsnummer.

- Dagens slutrapporter (räknare X och skattemässiga Z rapporter).
- Felhantering, t.ex. följande alternativ:

    - Försök att registrera skatteregistrering igen om ett nytt försök är möjligt, t.ex. om kvittoskrivaren inte är ansluten, om redo eller inte svarar, om skrivaren har slut på papper eller om det har fastnat i papper.
    - Senarelägg räkenskapsregistrering.
    - Hoppa över räkenskapsregistrering eller markera transaktionen som registrerad och inkludera informationskoder för att fånga orsaken till felet och ytterligare information.
    - Kontrollera tillgängligheten för kvittoskrivare innan en ny försäljningstransaktion öppnas eller en försäljningstransaktion slutförs.

### <a name="gift-cards"></a>Presentkort

I exemplet på integrering av kvittoskrivare implementeras följande regler som rör presentkort:

- Uteslut försäljningslinjer som är relaterade till *Utfärda presentkort* och *Lägg till presentkort* verksamhet från skattekvittot.
- Du kan inte skriva ut ett skattekvitto om det endast består av presentkortsrader.
- Dra av den totala mängden presentkort som har utfärdats eller debiteras på nytt i en transaktion från betalningsraderna på skatteinleveransen.
- Spara beräknade justeringar av betalningsrader i kanaldatabasen med en referens till en motsvarande räkenskapstransaktion.
- Betalning med presentkort betraktas som en vanlig betalning.

### <a name="customer-deposits-and-customer-order-deposits"></a>Kundinsättningar och kundorderdepositioner

Exemplet för integrering av kvittoskrivare implementerar följande regler som rör kunddepositioner och kundorderdepositioner:

- Skriv inte ut ett skattekvitto om en transaktion är en kundinsättning.
- Skriv inte ut ett skattekvitto om en transaktion endast innehåller en kundorderinsättning eller en återbetalning av en kundorderinsättning.
- Skriv ut beloppet för den tidigare betalade insättningen på ett skattekvitto för en upphämtningsoperation för kundorder.
- Dra av insättningsbeloppet för kundordern från betalningsrader när en kundorder skapas.
- Spara beräknade justeringar av betalningsrader i kanaldatabasen med en referens för en hybrid kundorder.

### <a name="limitations-of-the-sample"></a>Begränsningar i provet

- kvittoskrivaren stöder bara scenarier där moms inkluderas i priset. Därför måste alternativet **Inkludera moms** anges som **Ja** för både butiker och kunder.
- Dagliga rapporter (räkenskapsårets X och räkenskapsårets Z) skrivs ut med det inbäddade *skiftrapport*-formatet.
- Att skriva ut en streckkod på skattekvitton anses vara en potentiell anpassning, eftersom den här funktionen inte stöds i de inbäddade formaten och endast kan implementeras genom att använda den anpassningsbara rapporten **Super-format**.
- kvittoskrivaren har inte stöd för blandade transaktioner. Alternativet **Förbjud att blanda försäljning och returer i ett kvitto** bör anges till **Ja** i kassafunktionsprofiler.

## <a name="set-up-fiscal-integration-for-poland"></a>Ställ in räkenskapsintegration för Polen

Exemplet på integrering av kvittoskrivaren för Polen baseras på [räkenskapsintegrationsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\Posnet** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (till exempel [i version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). Proven [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) av en leverantör av skattedokument, vilket är ett filnamnstillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [ställa in ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md). 

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare (VM) i Microsoft Dynamics Lifecycle Services (LCS). Mer information finns i [Implementeringsriktlinjer för det skattemässiga skrivarintegreringsexemplet för Polen (äldre)](emea-pol-fpi-sample-sdk.md).
>
> Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

Slutför konfigurationsstegen för räkenskapsintegration som beskrivs i [ställa in räkenskapsintegration för Commerce-kanaler](setting-up-fiscal-integration-for-retail-channel.md).

1. [Ställa in process för räkenskapsregistrering](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Var noga med att notera inställningarna för den process för räkenskapsregistrering som är [specifika för det här kvittoskrivare integrering av prov](#set-up-the-registration-process).
1. [Ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Ställ in räkenskapsrapporter X/Y från POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Aktivera manuell körning av uppskjutna räkenskapsregistreringar](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Konfigurera kanalkomponenter](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Ställa in registrationsprocessen

Om du vill aktivera registreringsprocessen, följ dessa steg för att ställa in Commerce-administration. Mer information om [Ställ in räkenskapsintegrering för handelskanaler](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Ladda ner konfigurationsfiler för leverantören av skattedokument och skatteanslutningen:

    1. Öppna [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen.
    1. Välj en korrekt version av frisläppningen enligt din SDK/programversion (till exempel **[frisläppning/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Öppna **src \> FiscalIntegration \> Posnet**.
    1. Hämta konfigurationsfilen för räkenskapsdokumentprovidern på **CommerceRuntime \> DocumentProvider.PosnetSample \> Configuration \> DocumentProviderPosnetSample.xml** (t.ex. [filen för version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/CommerceRuntime/DocumentProvider.PosnetSample/Configuration/DocumentProviderPosnetSample.xml)).
    1. Ladda ner konfigurationsfilen för räkenskapskoppling på **HardwareStation \> ThermalDeviceSample \> Configuration \> ConnectorPosnetThermalFVEJ.xml** (t.ex. [filen för version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/HardwareStation/ThermalDeviceSample/Configuration/ConnectorPosnetThermalFVEJ.xml)).

    > [!WARNING]
    > På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Konfigurationsfilerna för det här exemplet för skatteintegration finns i följande mappar i Retail SDK på en utvecklar-VM i LCS:
    >
    > - **Konfigurationsfilen för räkenskapsdokumentprovidern:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml
    > - **Konfigurationsfil för räkenskapskoppling:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.Posnet.ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml
    > 
    > Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> delade Commerce-parametrar**. På fliken **allmänt** anger du alternativet **Aktivera räkenskapsintegration** till **Ja**.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegration \> Leverantörer av skattedokument** och läs in konfigurationsfilen för skattedokumentleverantören som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegration \> Räkenskapskopplingar** och läs in konfigurationsfilen för räkenskapskoppling för skattedokumentleverantören som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Funktionsprofiler för koppling**. Skapa en ny funktionsprofil för anslutning. Välj dokumentleverantören och den koppling som du läst in tidigare. Uppdatera [datamappningsinställningarna](#default-data-mapping) efter behov.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Tekniska profiler för koppling**. Skapa en ny teknisk profil för koppling och välj räkenskapskoppling som du laddade tidigare. Uppdatera [kopplingsinställningarna](#fiscal-connector-settings) efter behov.
6. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Grupper för skattekoppling**. Skapa en ny grupp för räkenskapskoppling för den funktionsprofil för koppling som du skapade tidigare.
7. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Processer för räkenskapsregistrering**. Skapa en ny räkenskapsregistrering och räkenskapsregistrering och välj den grupp för räkenskapskoppling som du skapade tidigare.
8. Gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**. Välj en funktionsprofil som är kopplad till butiken där registreringsprocessen ska aktiveras. På snabbfliken **Process för räkenskapsregistrering**, välj räkenskapsregistreringsprocessen som du skapade tidigare.
9. Gåt ill **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Kassaprofiler \> Maskinvaruprofiler**. Välj en maskinvaruprofil som är länkad till den Hardware Station som kvittoskrivare ska anslutas till. På snabbfliken **Kringutrustning för räkenskaper**, välj teknisk profil för koppling som du skapade tidigare.
10. Öppna distributionstidsplanen (**Retail och Commerce \> Retail och Commerce-IT \> Distributionsschema**) och välj jobb **1070** och **1090** för att överföra data till kanaldatabasen.

#### <a name="default-data-mapping"></a>Standarddatamappning

Följande standarddatamappning ingår i konfigurationen av leverantören av skattedokument som tillhandahålls som en del av exemplet på räkenskapsintegration.

- **Mappning av momssats (VAT)** – Mappning av procentvärden för moms som har ställts in för momskoderna till kvittoskrivare – specifika momssatser. Här är standardmappningen:

    ```
    0 : 23.00 ; 1 : 8.00 ; 2 : 5.00 ; 3 : 0.00
    ```

    Den första komponenten i varje par motsvarar ett momssatsnummer som konfigureras i kvittoskrivaren. Den andra komponenten motsvarar momssatsen. Mer information om momssatskonfigurationen för kvittoskrivare finns i POSNET-dokumentationen om momssatser.

- **Mappning av betalningsmedelstyp** – Mappningen av betalningsmetoder som har konfigurerats för butiken till betalningsformulär som stöds av kvittoskrivaren. Här är standardmappningen:

    ```
    0 : 0 ; 1 : 0 ; 2 : 2 ; 3 : 2 ; 4 : 0 ; 5 : 0 ; 6 : 0 ; 7 : 2 ; 8 : 0
    ```

    Den första komponenten i varje par representerar en betalningsmetod som ställts in för butiken. Den andra komponenten representerar motsvarande betalningsformulär som stöds av kvittoskrivaren. Mer information om betalningsformulär för kvittoskrivare finns i POSNET-dokumentationen. Du måste ändra exempelmappningen enligt betalningsmetoderna som är konfigurerade i programmet.

#### <a name="fiscal-connector-settings"></a>Inställningar för räkenskapskoppling

Följande inställningar ingår i den skatteanslutningskonfiguration som tillhandahålls som en del av det skattemässiga integrationsexemplet:

- **Anslutningssträng** – En sträng som beskriver detaljerna för anslutningen till enheten i ett format som stöds av drivrutinen. Mer information finns i dokumentationen för POSNET.
- **Datum- och tidssynkronisering** – Ett värde som anger om datum och tid för skrivaren måste synkroniseras med den anslutna maskinvaran.
- **Enhetens tidsgräns** – hur länge, i millisekunder, som drivrutinen väntar på ett svar från enheten. Mer information finns i dokumentationen för POSNET.

### <a name="configure-channel-components"></a>Konfigurera kanalkomponenter

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Mer information finns i [Implementeringsriktlinjer för det skattemässiga skrivarintegreringsexemplet för Polen (äldre)](emea-pol-fpi-sample-sdk.md).
>
> Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

#### <a name="set-up-the-development-environment"></a>Konfigurera en utvecklingsmiljö

Följ dessa steg för att ställa in en utvecklingsmiljö för att testa och utöka provet.

1. Eller hämta [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions)-databasen. Välj en korrekt version av frisläppningen enligt din SDK/programversion. För mer information, se [Hämta Retail SDK-exempel och referenspaket från GitHub och NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Öppna integrationslösningen för kvittoskrivaren på **Dynamics365Commerce.Solutions\\FiscalIntegration\\Posnet\\Posnet.sln** och skapa den.
1. Installera CRT-tillägg:

    1. Sök efter CRT installationsprogram:

        - **Commerce Scale Unit:** I mappen **Posnet\\ScaleUnit\\ScaleUnit.Posnet.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **ScaleUnit.Posnet.Installer**.
        - **Lokal CRT i Modern POS:** I mappen **Posnet\\ModernPOS\\ModernPOS.Posnet.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **ModernPOS.Posnet.Installer**.

    1. Starta CRT installationsprogrammet för filnamnstillägget från kommandorad:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.Posnet.Installer.exe install --verbosity 0
            ```

        - **Lokal CRT på Modern POS:**

            ```Console
            ModernPOS.Posnet.Installer.exe install --verbosity 0
            ```

1. Install tilläggen för Hardware Station:

    1. I mappen **Posnet\\HardwareStation\\HardwareStation.PosnetThermalFVFiscalPrinter.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **HardwareStation.PosnetThermalFVFiscalPrinter.Installer**.
    1. Starta installationsprogrammet för filnamnstillägget från kommandorad:

        ```Console
        HardwareStation.PosnetThermalFVFiscalPrinter.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Produktionsmiljö

Följ stegen i [Konfigurera en byggpipeline för ett skatteintegrationsprov](fiscal-integration-sample-build-pipeline.md) för att generera och släppa Cloud Scale Unit och självbetjäningsdistributionspaket för skatteintegreringsexemplet. Mall **Posnet build-pipeline.yml** YAML-filen finns i **Pipeline\\YAML_Files** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Design av tilläggen

Exemplet på integrering av kvittoskrivaren för Polen baseras på [räkenskapsintegrationsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\Posnet** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (till exempel [i version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). Proven [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) av en leverantör av skattedokument, vilket är ett filnamnstillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [ställa in ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md). 

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Mer information finns i [Implementeringsriktlinjer för det skattemässiga skrivarintegreringsexemplet för Polen (äldre)](emea-pol-fpi-sample-sdk.md). Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

### <a name="commerce-runtime-extension-design"></a>Utbyggbarhetdesign för Commerce Runtime

Syftet med tillägget som är en skattedokument leverantör är att generera utskriftspecifika dokument och hantera svar från räkenskapsregistreringsutskrift. Det här filnamnstillägget genererar en uppsättning skrivarspecifika kommandon i JSON-format (JavaScript Object Notation) som definieras i POSNET-specifikation 19-3678.

#### <a name="request-handler"></a>Begärandehanterare

**DocumentProviderPosnetProtocol** begäranhanteraren är ingångspunkten för begäran om att generera dokument från skatteskrivaren.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Commerce-administration.

Kopplingen stöder följande begäranden:

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett utskriftsspecifikt dokument som ska registreras i kvittoskrivaren.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på. För närvarande stöds följande händelser: försäljning, utskrift av X-rapport och utskrift av Z-rapport.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av skattedokument finns på **src\\FiscalIntegration\\Posnet\\CommerceRuntime\\DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Syftet med den här filen är att aktivera inställningar för skattedokumentprovidern som ska konfigureras från Commerce-administration. Filformatet justeras med kraven för konfiguration av räkenskapsintegration.

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget som är en räkenskapskoppling är att kommunicera med kvittoskrivare. Det här filnamnstillägget anropar POSNET-drivrutinens funktioner för att skicka kommandon som CRT-tillägget genererar till kvittoskrivaren. Den hanterar även enhetsfel.

#### <a name="request-handler"></a>Begärandehanterare

**FiscalPrinterHandler** begäranhanteraren är startpunkten för hantering av begäranden till kringutrustning för räkenskaper.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Commerce-administration.

Kopplingen stöder följande begäranden:

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till skrivare och returnerar svaret från kvittoskrivaren.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av enheten.
- **InitializeFiscalDeviceRequest** – Denna begäran används för skrivarinitiering.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av anslutningsprogram på **src\\FiscalIntegration\\Posnet\\HardwareStation\\ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Syftet med filen är att aktivera inställningar för räkenskapskoppling som ska konfigureras från Commerce-administration. Filformatet justeras med kraven för konfiguration av räkenskapsintegration.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
