---
title: Exempel på skatteregistreringstjänsten för Tjeckien
description: I denna artikel finns en översikt över exemplet på räkenskapsintegrering för Tjeckien i Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-04-01
ms.openlocfilehash: de26b038009d8bf3518c67389c96aade19a0b65b
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631299"
---
# <a name="fiscal-registration-service-integration-sample-for-the-czech-republic"></a>Exempel på skatteregistreringstjänsten för Tjeckien

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

I denna artikel finns en översikt över exemplet på räkenskapsintegrering för Tjeckien i Microsoft Dynamics 365 Commerce.

För att uppfylla lokala räkenskapskrav för kassaapparater i Tjeckien Dynamics 365 Commerce funktionaliteten för Tjeckien inkluderar ett exempel på integrering av kassan (POS) med en extern skatteregistreringstjänst. Det här exemplet utökar [funktionen räkenskapsintegrering](fiscal-integration-for-retail-channel.md). Den är baserad på [EFR (elektroniskt skatteregister)](https://efsta.org/sicherheitsloesungen/) lösningar från [EFSTA](https://efsta.org/) och möjliggör kommunikation med EFR-tjänsten via HTTPS-protokollet. EFR-tjänsten säkerställer elektronisk registrering av försäljning (Elektronická evidence tržeb \[EET\]). Med andra ord ser det till att försäljningsdata överförs online till en skattetjänst från skattemyndigheterna. EFR-tjänsten bör ha en värd för antingen Commerce Hardware Station eller en separat maskin som kan kopplas till från maskinvarutjänsten. Exemplet tillhandahålls i form av källkod och är en del av Commerce Software Development Kit (SDK).

Microsoft släpper inte någon maskinvara, programvara eller dokumentation från EFSTA. För information om hur du får EFR-lösning och använder den, kontakta [EFSTA](https://efsta.org/kontakt/).

## <a name="scenarios"></a>Scenarier

Följande scenarier täcks av integreringsexempel för skatteregistreringstjänster för Tjeckien.

- Registrering av kontanttransaktioner i skatteregistreringstjänsten.

    - Skicka detaljerade transaktionsdata till skatteregistreringstjänsten. Dessa data inkluderar försäljningsradinformation och information om rabatter, betalningar och skatter. Skatteregistreringstjänsten skickar ytterligare data till skattemyndighetens webbtjänst och får en bekräftelse från den som inkluderar transaktionens skatteidentifieringskod.
    - Få ett svar från skatteregistreringstjänsten. Det här svaret omfattar räkenskapsdata som skatte-ID och säkerhetskod för transaktionen osv.
    - Skriv ut räkenskapsdata för en registrerad transaktion på inleveransen.

- Registrering av presentkortsåtgärder och kunddepositioner i skatteregistreringstjänsten.

    - Pengar utfärdas eller läggs till på presentkortet.
    - Registrera en kundkontoinsättning.
    - Skapa en kundorder och registrera en insättning för ordern.
    - Redigera en kundorder och åsidosätta en insättning för ordern.
    - Annullera en kundorder och återbetalning en insättning för ordern.

- Felhantering, t.ex. följande alternativ.

    - Försöka skapa en skatteregistrering igen om ett nytt försök är möjligt, t.ex. om räkenskapsårets registreringsservice inte är tillgänglig, om räkenskapsregistreringen är redo eller om den inte svarar.
    - Senarelägg skatteregistrering.
    - Hoppa över räkenskapsregistrering eller markera transaktionen som registrerad och inkludera informationskoder för att fånga orsaken till felet och ytterligare information.
    - Kontrollera tillgängligheten för räkenskapsregistreringstjänsten innan en ny försäljningstransaktion öppnas eller en försäljningstransaktion slutförs.

### <a name="gift-cards"></a>Presentkort

I exemplet på integrering av räkenskapsregistreringstjänsten följande regler som rör presentkort.

- Försäljningsrader som är relaterade till *Utfärda presentkort* eller *Lägg till presentkort* i en försäljningstransaktion markeras med ett särskilt attribut när transaktionen registreras i skatteregistreringstjänsten.
- En betalning med presentkort betraktas som en vanlig betalning och markeras med ett särskilt attribut när transaktionen registreras i skatteregistreringstjänsten.

### <a name="customer-account-deposits-and-customer-order-deposits"></a>Kundkontoinsättningar och kundorderdepositioner

Exemplet för integrering av räkenskapsregistreringstjänsten implementerar följande regler som rör kundkontodepositioner och kundorderdepositioner.

- En transaktion som rör en insättning på ett kundkonto eller en kundorderinsättning registreras i skatteregistreringstjänsten som en enskild radtransaktion och är markerad med ett särskilt attribut. Insättningsmomsgruppen anges på den här raden.
- När en kundorder skapas, det vill säga en kundorder som innehåller produkter som kan utföras av kunden, samt produkter som ska hämtas eller levereras senare, innehåller transaktionen som registrerats på skatteregistreringstjänsten rader för de produkter som utförs samt en rad för orderinsättningen.
- En betalning från ett kundkonto betraktas som en vanlig betalning och markeras med ett särskilt attribut när transaktionen registreras i skatteregistreringstjänsten.
- Insättningsbeloppet för kundordern som används på en upphämtningsåtgärd för kundorder betraktas som en vanlig betalning och markeras med ett särskilt attribut när transaktionen registreras i skatteregistreringstjänsten.

### <a name="offline-registration"></a>Offlineregistrering

Om skatteregistreringstjänsten inte överför transaktionsdata till skattemyndighetens webbtjänst (till exempel på grund av svarstids tidsgränsen) och får en bekräftelse från webbtjänsten (det vill säga transaktionens skatte-ID-kod) genererar den en lokal signatur för transaktionen och inkluderar den och en särskild felkod i svaret. Skatteregistreringstjänsten skickar om transaktioner i ursprunglig ordning i bakgrunden när nätverksanslutningen har återställts.

### <a name="limitations-of-the-sample"></a>Begränsningar i provet

Räkenskapsregistreringstjänsten stöder bara scenarier där moms inkluderas i priset. Därför måste alternativet **Inkludera moms** anges som **Ja** för både butiker och kunder.

## <a name="set-up-commerce-for-the-czech-republic"></a>Konfigurera Commerce för Tjeckien

Det här avsnittet beskriver inställningar för Commerce som avser och rekommenderas för Tjeckien. Mer information finns i [Startsida för Commerce](../index.md).

Om du vill använda den Tjeckien-specifika funktionen måste du ange följande inställningar.

- I den primära adressen för den juridiska personen, ange fältet **land/region** till **CZE** (Tjeckien).
- I POS-funktionalitetsprofilen för varje butik som finns i land, ställ in **ISO-kod** till **CZ** (land).

Du måste ange följande allmänna inställningar för Tjeckien. Observera att du måste köra lämpliga distributionsjobb när du har slutfört inställningarna.

### <a name="set-up-vat-per-czech-republic-requirements"></a>Ställa in moms per Tjeckien-krav


Du måste skapa momskoder, momsgrupper och artikelmomsgrupper. Du måste även konfigurera momsinformation för produkter och tjänster. Mer information om hur du konfigurerar och använder moms finns i [Momsöversikt](../../finance/general-ledger/indirect-taxes-overview.md).

### <a name="set-up-stores"></a>Skapa butiker

På sidan **Alla butiker** uppdaterar du butiksinformation. Du måste speciellt konfigurera följande parametrar.

- I fältet **Momsgrupp** anger du en momsgrupp som ska användas för försäljning till standardkund.
- Ange alternativet **Priserna inkluderar moms** till **Ja**.
- Ställ in fältet **Namn** på företagsnamnet. Den här ändringen hjälper till att garantera att företagsnamnet visas på ett försäljningskvittot. Alternativt kan du kan lägga till företagsnamnet på layouten av försäljningskvittot i fritt format.
- Ange fältet **Skatteidentifieringsnummer (TIN)** så att det inkluderar företagets identifieringnummer. Den här ändringen hjälper till att garantera att företagets identifieringnummer visas på ett försäljningskvittot. Alternativt kan du kan lägga till företagets identifieringnummer på försäljningskvittot i fritt format.

### <a name="set-up-functionality-profiles"></a>Ställa in funktionsprofiler

Ställa in kassafunktionsprofiler.

- På snabbfliken **Inleveransnumrering** ställer du in inleveransnumrering genom att skapa eller uppdatera poster för transaktionstyperna **Försäljning**, **Försäljningsorder** och **Retur**.

### <a name="set-up-registration-numbers"></a>Ställ in registreringsnummer

1. Gå till **Organisationsadministration \> Global adressbok \> Registrationstyper \> Registrationstyper**. Skapa en ny registreringstyp. Ange fältet **Land/region** till **CZE** (Tjeckien) och gör det begränsat till Organisation.
2. Gå till **Organisationsadministration \> Global adressbok \> Registrationtyper \> Registreringskategorier**. Skapa en ny registreringskategori. Välj registreringstyp i det föregående steget och ställ in **registreringskategorin** på **Affärsförutsättning-ID**.
3. Gå till **Organisationsadministration \> Organisationer \> Driftenheter**. För varje butik i Tjeckien väljer du den enhet som är relaterad till butiken. På snabbfliken **Adress**, expandera **Fler alternativ** och välj listruta **Avancerat**. 
4. På sidan **Hantera adresser** måste du ange följande inställningar.

    - På snabbfliken **Adress** på fältet **land/region** till **CZE**.
    - På snabbfliken **Registrerings-ID** skapa en ny post. Välj den registreringstyp som skapats tidigare och ange registreringsnumret.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Konfigurera anpassade fält så att de kan användas i kvittoformat för försäljningskvitton

Du kan konfigurera språktext och anpassade fält som används i kassakvittoformat. Standardföretaget för den användare som skapar kvittoinställningen bör vara samma juridiska person där språktextinställningarna skapas. Du kan också skapa samma språktexter i både användarens standardföretag och den juridiska personen i butiken som installationen har skapats för.

På sidan **Språktext** kan du lägga till följande poster för etiketterna för de anpassade fälten för kvittolayout. Observera att värdena **Språk-ID**, **Text-ID** och **Text** som visas i tabellen bara är exempel. Du kan ändra dem för att uppfylla dina krav. Värdena för **text-ID** som du använder måste dock vara unika och de måste vara lika med eller större än 900001.

Lägg till följande kassaetiketter i avsnittet **kassa** på sidan **språktext** från tabellen.

| Språk-ID | Text-ID | Text                   |
|-------------|---------|------------------------|
| en-US       | 900001  | ID provozovny/pokladny |
| en-US       | 900002  | BKP                    |
| en-US       | 900003  | PKP                    |
| en-US       | 900004  | FIK                    |
| en-US       | 900005  | Info                   |
| en-US       | 900006  | Löpnummer        |

På sidan **Anpassade fält** kan du lägga till följande poster för anpassade fält för kvittolayouter. Observera att värdena **Text-ID för rubrik** måste motsvara de värden för **Text-ID** som du angav på sidan **språktext**:

| Namn                 | Typ    | Text-ID för rubrik |
|----------------------|---------|-----------------|
| TLT                  | Inleverans | 900001          |
| SEC                  | Inleverans | 900002          |
| SIGN                 | Inleverans | 900003          |
| FISCAL               | Inleverans | 900004          |
| INFO                 | Inleverans | 900005          |
| CONTINUOUSNUMBER     | Inleverans | 900006          |

> [!NOTE]
> Det är viktigt att du anger rätt anpassade fältnamn, så som listas i föregående register. Om fel anpassat fältnamn saknas data i kvittona.

### <a name="configure-receipt-formats"></a>Konfigurera kvittoformat

För varje kvittoformat som krävs, ändra värdet för fältet **Utskriftssätt** till **Skriv alltid ut**.

I Layoutdesigner för kvitto, lägg till följande anpassade fält i lämpliga kvittoavdelningar. Observera att fältnamn motsvarar de språktexter som du definierade i föregående avsnitt.

- **Rubrik:** Lägg till följande fält.

    - **Butiksnamn** och **momsidentifieringsnummer**: dessa fält används för att skriva ut företagsnamnet och identitetsnumret på kvitton. Alternativt kan du kan lägga till företagsnamn och identitetsnummer på layouten i fritt format.
    - **Butiksadress**, **datum**, **Tid, 24 h**, **kvittonummer**, och **registreringsnummer**.
    - **Sekvensnummer**: detta fält identifierar numret på kontanttransaktionen i skatteregistreringstjänsten.

- **Rader:** Lägg till följande fält.

    - **Artikelnamn**
    - **Antal**
    - **Totalpris inkl. moms**

- **Sidfot:** Lägg till följande fält.

    - Betalningsfält så att betalningsbeloppen för varje betalningsmetod skrivs ut. Till exempel fältet **Namn på betalningsmedel** och **Belopp för betalningsmedel** till en rad i layouten.
    - **ID provozovny/pokladny**: detta fält skriver ut identifierarna för affärslokalen och kassaapparaten.
    - **BKP**: I det här fältet skrivs den skattebetalarsäkerhetskod som tilldelats av skatteregistreringstjänsten ut.
    - **FIK**: detta fält skriver ut den skattemässiga identifieringskoden för transaktionen som tilldelas av skattemyndigheternas webbtjänst i händelse av framgångsrik onlineregistrering.
    - **PKP**: detta fält skriver ut skattebetalarens signaturkod som genereras av skatteregistreringstjänsten vid offlineregistrering.
    - **Info**: I det här fältet skrivs ytterligare information ut från skatteregistreringstjänsten.

Mer information om hur du arbetar med kvittoformat finns i [Ställ in och designa inleveransformat](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-the-czech-republic"></a>Ställ in räkenskapsintegrering för Tjeckien

Exemplet på integrering av räkenskapsregistreringstjänsten för Tjeckien baseras på [räkenskapsintegreringsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Commerce SDK. Exemplet finns i mappen **src\\FiscalIntegration\\Efr** i databasen [Dynamics 365 Commerce-lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/). [Exemplet](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) består av en leverantör av skattedokument, vilket är ett tillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Commerce SDK finns i [Hämta Commerce SDK exempel och referenspaket från GitHub och NuGet](../dev-itpro/retail-sdk/sdk-github.md) och [Konfigurera en bygg-pipeline för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md).

> [!NOTE]
> Exemplet på integrering av skatteregistreringstjänsten för Tjeckien finns i Commerce SDK från och med Commerce version 10.0.29. I Commerce version 10.0.28 måste du använda föregående version av Retail SDK på en virtuell utvecklare (VM) i Microsoft Dynamics Lifecycle Services (LCS). Mer information finns i [Implementeringsriktlinjer för det skattemässiga integreringsexemplet för Tjeckien (äldre)](emea-cze-fi-sample-sdk.md).

Slutför konfigurationsstegen för räkenskapsintegrering som beskrivs i [konfigurera räkenskapsintegrering för Commerce-kanaler](setting-up-fiscal-integration-for-retail-channel.md):

1. [Ställa in process för räkenskapsregistrering](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Var noga med att notera inställningarna för den process för räkenskapsregistrering som är [specifika för det här exemplet på skatteregistreringstjänsten](#set-up-the-registration-process).
1. [Ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Aktivera manuell körning av periodiserade skatteregistreringar](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).
1. [Konfigurera kanalkomponenter](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Ställa in registrationsprocessen

Om du vill aktivera registreringsprocessen, följ dessa steg för att konfigurera Commerce headquarters. Mer information om [Ställ in räkenskapsintegrering för handelskanaler](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Ladda ner konfigurationsfiler för providern av skattedokument och skatteanslutningen:

    1. Öppna [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen.
    1. Välj en korrekt version av frisläppningen enligt din SDK/programversion.
    1. Öppna **src \> FiscalIntegration \> Efr**.
    1. Ladda ner konfigurationsfilen för finansiell dokumentleverantör på **Konfigurationer \> DocumentProviders \> DocumentProviderFiscalEFRSampleCzech.xml**.
    1. Ladda ner konfigurationsfilen för räkenskapskoppling på **Konfigurationer \> Anslutningar \> ConnectorEFRSample.xml**.

    > [!NOTE]
    > I Commerce version 10.0.28 måste du använda föregående version av Retail SDK på en virtuell utvecklare (VM) i LCS. Konfigurationsfilerna för det här exemplet för skatteintegrering finns i följande mappar i Retail SDK på en utvecklar-VM i LCS:
    >
    > - **Konfigurationsfilen för räkenskapsdokumentprovidern:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleCzech.xml
    > - **Konfigurationsfil för räkenskapskoppling:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration\\ConnectorEFRSample.xml

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> delade Commerce-parametrar**. På fliken **allmänt** anger du alternativet **Aktivera räkenskapsintegrering** till **Ja**.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Leverantörer av skattedokument** och läs in konfigurationsfilen för skattedokumentprovidern som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Räkenskapskopplingar** och läs in konfigurationsfilen för räkenskapskoppling för skattedokumentprovidern som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Funktionsprofiler för koppling**. Skapa en ny funktionsprofil för anslutning. Välj dokumentprovidern och den koppling som du läst in tidigare. Uppdatera [datamappningsinställningarna](#default-data-mapping) efter behov.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Tekniska profiler för koppling**. Skapa en ny teknisk profil för koppling och välj räkenskapskoppling som du laddade tidigare. Uppdatera [kopplingsinställningarna](#fiscal-connector-settings) efter behov.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Grupper för skattekoppling**. Skapa en ny grupp för räkenskapskoppling för den funktionsprofil för koppling som du skapade tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Processer för räkenskapsregistrering**. Skapa en ny räkenskapsregistrering och räkenskapsregistrering och välj den grupp för räkenskapskoppling som du skapade tidigare.
1. Gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**. Välj en funktionsprofil som är kopplad till butiken där registreringsprocessen ska aktiveras. På snabbfliken **Process för räkenskapsregistrering**, välj räkenskapsregistreringsprocessen som du skapade tidigare.
1. Gåt ill **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Kassaprofiler \> Maskinvaruprofiler**. Välj en maskinvaruprofil som är länkad till den Hardware Station som skatteregistreringstjänsten ska anslutas till. På snabbfliken **Kringutrustning för räkenskaper**, välj teknisk profil för koppling som du skapade tidigare.
1. Öppna distributionstidsplanen (**Retail och Commerce \> Retail och Commerce-IT \> Distributionsschema**) och välj jobb **1070** och **1090** för att överföra data till kanaldatabasen.

#### <a name="default-data-mapping"></a>Standarddatamappning

Följande standarddatamappning ingår i konfigurationen av providern av skattedokument som tillhandahålls som en del av exemplet på räkenskapsintegrering.

- **Mappning av momssats** – Mappning av procentvärden för moms som har ställts in för momskoderna till värden i attributet **TaxG** (momsgrupp) i förfrågningar som skickas till skattetjänsten. Här är standardmappningen:

    ```
    A: 21.00; B: 15.00; C: 10.00; Z: 0.00
    ```

    Den första komponenten i varje par representerar en momsgrupp som stöds av EFR-räkenskapsregistreringstjänsten. Den andra komponenten motsvarar momssatsen. Mer information om momsgrupper som EFR stöder för Tjeckien finns i [EFR-referensen](https://public.efsta.net/efr/).

- **Standardmappning för momsgrupp** – Alla momsbelopp som inte kan kopplas till någon av de fördefinierade momsgrupperna tilldelas standardmomsgruppen. Här är standardmappningen:

    ```
    A
    ```

- **Mappning av momsgrupp** – Kundinsättningsbelopp och insättningsbelopp för kundorder tilldelas insättningsmomsgruppen. Här är standardmappningen:

    ```
    Z
    ```

#### <a name="fiscal-connector-settings"></a>Inställningar för räkenskapskoppling

Följande inställningar ingår i den skatteanslutningskonfiguration som tillhandahålls som en del av det skattemässiga integreringsexemplet:

- **Slutpunktsadress** – URL:en för skatteregistreringstjänsten.
- **Timeout** – hur länge, i millisekunder, som räkenskapskoppling väntar på ett svar från räkenskapsregistreringstjänst.

### <a name="configure-channel-components"></a>Konfigurera kanalkomponenter

> [!NOTE]
> - Exemplet på integrering av skatteregistreringstjänsten för Tjeckien finns i Commerce SDK från och med Commerce version 10.0.29. I Commerce version 10.0.28 måste du använda föregående version av Retail SDK på en virtuell utvecklare (VM) i LCS. Mer information finns i [Implementeringsriktlinjer för det skattemässiga integreringsexemplet för Tjeckien (äldre)](emea-cze-fi-sample-sdk.md).
> - Commerce-exempel som distribueras i din miljö uppdateras inte automatiskt när du tillämpar service- eller kvalitetsuppdateringar på Commerce-komponenter. Du måste uppdatera de obligatoriska exemplen manuellt.

#### <a name="set-up-the-development-environment"></a>Konfigurera en utvecklingsmiljö

Följ dessa steg för att konfigurera en utvecklingsmiljö för att testa och utöka provet.

1. Eller hämta [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions)-databasen. Välj en korrekt version av frisläppningen enligt din SDK/programversion. För mer information, se [Hämta Commerce SDK-exempel och referenspaket från GitHub och NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Öppna EFR-lösningen på **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln** och bygg den.
1. Installera CRT-tillägg:

    1. Sök efter CRT installationsprogram:

        - **Commerce Scale Unit:** I mappen **Efr\\ScaleUnit\\ScaleUnit.EFR.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **ScaleUnit.EFR.Installer**.
        - **Lokal CRT i Modern POS:** I mappen **Efr\\ModernPOS\\ModernPOS.EFR.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **ModernPOS.EFR.Installer**.

    1. Starta CRT installationsprogrammet för tillägget från kommandorad:

        - **Commerce Scale Unit.**

            ```Console
            ScaleUnit.EFR.Installer.exe install --verbosity 0
            ```

        - **Lokal CRT på Modern POS:**

            ```Console
            ModernPOS.EFR.Installer.exe install --verbosity 0
            ```

1. Installera tillägg för anslutningsprogram för skatt:

    Du kan installera tillägg för anslutningsprogram för skatt i [maskinvarustationen](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) eller [kassaapparaten](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

    1. Install tilläggen för Hardware Station:

        1. Lokal i mappen **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461**, hitta installationsprogrammet **HardwareStation.EFR.Installer**.
        1. Starta installationsprogrammet för tillägget från kommandoraden genom att köra följande kommando.

            ```Console
            HardwareStation.EFR.Installer.exe install --verbosity 0
            ```

    1. Installera kassatillägg:

        1. Öppna exempellösningen för kassaanslutningsprogram för skatt på **Dynamics365Commerce.Solutions\\FiscalIntegration\\PosFiscalConnectorSample\\Contoso.PosFiscalConnectorSample.sln** och bygg den.
        1. I mappen **PosFiscalConnectorSample\\StoreCommerce.Installer\\bin\\Debug\\net461** letar du upp installationsprogrammet **Contoso.PosFiscalConnectorSample.StoreCommerce.Installer**.
        1. Starta installationsprogrammet för tillägget från kommandoraden genom att köra följande kommando.

            ```Console
            Contoso.PosFiscalConnectorSample.StoreCommerce.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Produktionsmiljö

Följ stegen i [Konfigurera en byggpipeline för ett skatteintegreringsprov](fiscal-integration-sample-build-pipeline.md) för att generera och släppa Cloud Scale Unit och självbetjäningsdistributionspaket för skatteintegreringsexemplet. Mall **EFR build-pipeline.yml** YAML-filen finns i **Pipeline\\YAML_Files** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Design av tilläggen

Exemplet på integrering av räkenskapsregistreringstjänsten för Tjeckien baseras på [räkenskapsintegreringsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Commerce SDK. Exemplet finns i mappen **src\\FiscalIntegration\\Efr** i databasen [Dynamics 365 Commerce-lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/). [Exemplet](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) består av en leverantör av skattedokument, vilket är ett tillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Commerce SDK finns i [Hämta Commerce SDK exempel och referenspaket från GitHub och NuGet](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [Konfigurera en bygg-pipeline för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md).

> [!NOTE]
> Exemplet på integrering av skatteregistreringstjänsten för Tjeckien finns i Commerce SDK från och med Commerce version 10.0.29. I Commerce version 10.0.28 måste du använda föregående version av Retail SDK på en virtuell utvecklare (VM) i LCS. Mer information finns i [Implementeringsriktlinjer för det skattemässiga integreringsexemplet för Tjeckien (äldre)](emea-cze-fi-sample-sdk.md).

### <a name="commerce-runtime-extension-design"></a>Utbyggbarhetdesign för Commerce Runtime

Syftet med tillägget som är en skattedokument leverantör är att generera tjänstspecifika dokument och hantera svar från räkenskapsregistreringstjänsten.

#### <a name="request-handler"></a>Begärandehanterare

Det finns en enskild **DocumentProviderEFRFiscalCZE** begäranhanterare för dokumentleverantör, som används för att generera skattedokument för skatteregistreringstjänsten.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Commerce headquarters.

Kopplingen stöder följande begäranden.

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett tjänstspecifikt dokument som ska registreras i räkenskapsregistreringstjänst.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på. För närvarande stöds följande händelser: försäljning, insättning av kundkonto och insättning av kundorder.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Denna begäran returnerar svaret från skatteregistreringstjänsten. Svaret serialiseras så att det går att spara.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av skattedokument finns på **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleCzech.xml** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Syftet med den här filen är att aktivera inställningar för skattedokumentprovidern som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering.

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget som är en räkenskapskoppling är att kommunicera med räkenskapsregistreringstjänsten. Hardware Station tillägg använder HTTP-protokollet för att skicka dokument som CRT-tillägget genererar till räkenskapsregistreringstjänsten. Den hanterar också svar som tas emot från räkenskapsregistreringstjänsten.

#### <a name="request-handler"></a>Begärandehanterare

**EFRHandler** begäranhanteraren är startpunkten för hantering av begäranden till räkenskapsregistreringstjänst.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Commerce headquarters.

Kopplingen stöder följande begäranden.

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till räkenskapsregistreringstjänsten och returnerar ett svar från den.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av tjänsten för räkenskapsregistrering.
- **InitializeFiscalDeviceRequest** – den här begäran används för initiera tjänsten för räkenskapsregistrering.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av anslutningsprogram på **src\\FiscalIntegration\\Efr\\konfigurationer\\anslutningsprogram\\ConnectorEFRSample.xml** i [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen. Syftet med filen är att aktivera inställningar för räkenskapskoppling som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering.

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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
