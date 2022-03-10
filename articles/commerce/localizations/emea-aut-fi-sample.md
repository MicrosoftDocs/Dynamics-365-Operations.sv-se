---
title: Exempel på skatteregistreringstjänst för Österrike
description: I det här avsnittet finns en översikt över exemplet på räkenskapsintegration för Österrike i Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: d720bffb98965bdc0276660d2a2e50d2bf155e74
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077175"
---
# <a name="fiscal-registration-service-integration-sample-for-austria"></a>Exempel på skatteregistreringstjänst för Österrike

[!include[banner](../includes/banner.md)]

I det här avsnittet finns en översikt över exemplet på räkenskapsintegration för Österrike i Microsoft Dynamics 365 Commerce.

För att uppfylla lokala räkenskapskrav för kassaregister i Österrike Dynamics 365 Retail funktionaliteten för Österrike inkluderar ett exempel på integration av kassan (POS) med en extern skatteregistreringstjänst. Det här exemplet utökar [funktionen räkenskapsintegrering](fiscal-integration-for-retail-channel.md). Den är baserad på [EFR (elektroniskt skatteregister)](https://www.efsta.eu/at/fiskalloesungen/oesterreich) lösningar från [EFSTA](https://www.efsta.eu/at/) och möjliggör kommunikation med EFR-tjänsten via HTTPS-protokollet. EFR-tjänsten bör ha en värd för antingen Retail Hardware eller en separat maskin som kan kopplas till från maskinvarutjänsten. Exemplet tillhandahålls i form av källkod och är en del av Retail Software Development Kit (SDK).

Microsoft släpper inte någon maskinvara, programvara eller dokumentation från EFSTA. För information om hur du får EFR-lösning och använder den, kontakta [EFSTA](https://www.efsta.eu/at/kontakt).

## <a name="scenarios"></a>Scenarier

Följande scenarier täcks av integrationsexempel för skatteregistreringstjänster för Österrike:

- Registrering av kontanttransaktioner i skatteregistreringstjänsten:

    - Skicka detaljerade transaktionsdata till skatteregistreringstjänsten. Dessa data inkluderar försäljningsradinformation och information om rabatter, betalningar och skatter.
    - Få ett svar från skatteregistreringstjänsten. Det här svaret inkluderar en digital signatur och en länk till den registrerade transaktionen.
    - Registrera skatter och mappa dem till skatteregistreringstjänstens momskoder.
    - Skriv ut QR-koden för en registrerad transaktion på inleveransen.

- Registrering av presentkortsoperationer och kunddepositioner som icke-kontanttransaktioner i skatteregistreringstjänsten:

    - Pengar utfärdas eller läggs till på presentkortet.
    - Registrera en kundkontoinsättning.
    - Registrera en kundorderinsättning.

- Registrering av icke-försäljningstransaktioner och händelser som icke-kontanttransaktioner i skatteregistreringstjänsten:

    - Öppna skift och stäng skift
    - Startbelopp, växelpost och borttagning av betalningsmedel
    - Åsidosätt pris
    - Åsidosätt moms
    - Skriv ut kvittokopia
    - Öppna kassalåda
    - Skriv ut X-rapport
    - Skriv ut Z-rapport

- Skriva ut rapporter vid dagens slut (X/Z-rapporter) som har Österrike-specifika fält:

    - Totalt antal produkter eller tjänster som levererats till kunder
    - Uppdelning av moms per momssats
    - Uppdelning av betalningar per kassa/kassaoperatör
    - Prisrabatter och returer som minskar den dagliga försäljningen
    - Nollförsäljning (presentartikel)

- Felhantering, t.ex. följande alternativ:

    - Försöka skapa en skatteregistrering igen om ett nytt försök är möjligt, t.ex. om räkenskapsårets registreringsservice inte är tillgänglig, om räkenskapsregistreringen är redo eller om den inte svarar.
    - Senarelägg räkenskapsregistrering.
    - Hoppa över räkenskapsregistrering eller markera transaktionen som registrerad och inkludera informationskoder för att fånga orsaken till felet och ytterligare information.
    - Kontrollera tillgängligheten för räkenskapsregistreringstjänsten innan en ny försäljningstransaktion öppnas eller en försäljningstransaktion slutförs.

### <a name="gift-cards"></a>Presentkort

I exemplet på integrering av räkenskapsregistreringstjänsten följande regler som rör presentkort:

- Uteslut försäljningslinjer som är relaterade till *Utfärda presentkort* och *Lägg till presentkort* verksamhet från kontanttransaktion. Istället för att registrera de raderna som en del av en kontanttransaktion registrerar du dem som en separat icke kontanttransaktion i skatteregistreringstjänsten.
- Skriv inte ut en momsgruppsuppdelning och en QR-kod på ett kvitto om inleveransen endast består av presentkortsrader.
- Skriv ut den totala mängden presentkort som har utfärdats eller debiteras på nytt i en transaktion separat från det kontanta transaktionsbeloppet på kvittot.
- Spara beräknade justeringar av betalningsrader i kanaldatabasen med en referens till en motsvarande räkenskapstransaktion.
- Betalning med presentkort betraktas som en vanlig betalning.

### <a name="customer-deposits-and-customer-order-deposits"></a>Kundinsättningar och kundorderdepositioner

Exemplet för integrering av räkenskapsregistreringstjänsten implementerar följande regler som rör kunddepositioner och kundorderdepositioner:

- Registrera en icke kontanttransaktion om en transaktion är en kundinsättning.
- Registrera en icke kontanttransaktion om en transaktion endast innehåller en kundorderinsättning eller en återbetalning av en kundorderinsättning.
- Dra av insättningsbeloppet för kundordern från betalningsrader när en kundorder skapas.
- Spara beräknade justeringar av betalningsrader i kanaldatabasen med en referens för en hybrid kundorder.

### <a name="limitations-of-the-sample"></a>Begränsningar i provet

Räkenskapsregistreringstjänsten stöder bara scenarier där moms inkluderas i priset. Därför måste alternativet **Inkludera moms** anges som **Ja** för både butiker och kunder.

## <a name="set-up-commerce-for-austria"></a>Ställa in Commerce för Österrike

Det här avsnittet beskriver inställningar för Commerce som avser och rekommenderas för Österrike. Mer information om hur du ställer in information finns [på startsidan för Commerce](../index.md).

Om du vill använda den Österrike-specifika funktionen måste du ange följande inställningar:

- I den primära adressen för den juridiska personen, ställ in fältet **Country/region** till **AUT** (Österrike).
- I POS-funktionalitetsprofilen för varje butik som finns i Österrike, ställ in **ISO-kod** till **AT** (Österrike).

Du måste ange följande allmänna inställningar för Österrike. Observera att du måste köra lämpliga distributionsjobb när du har slutfört inställningarna.

### <a name="set-up-vat-per-austrian-requirements"></a>Ställa in moms per österrikiskt krav

Du måste skapa momskoder, momsgrupper och artikelmomsgrupper. Du måste även ställa in momsinformation för produkter och tjänster. Mer information om hur du ställer in och använder moms finns i [Momsöversikt](../../finance/general-ledger/indirect-taxes-overview.md).

På försäljningsinleveranser kan du skriva ut en förkortad kod för en momskod (till exempel "A" eller "B"). Om du vill göra funktionen tillgänglig ställer du in fältet **Utskriftskod** på sidan **Momskoder**.

### <a name="set-up-stores"></a>Skapa butiker

På sidan **Alla butiker** uppdaterar du butiksinformation. Du måste speciellt ställa in följande parametrar:

- I fältet **Momsgrupp** anger du en momsgrupp som ska användas för försäljning till standardkund.
- Ange alternativet **Priserna inkluderar moms** till **Ja**.
- Ställ in fältet **Namn** på företagsnamnet. Den här ändringen hjälper till att garantera att företagsnamnet visas på ett försäljningskvittot. Alternativt kan du kan lägga till företagsnamnet på layouten av försäljningskvittot i fritt format.
- Ange fältet **Skatteidentifieringsnummer (TIN)** så att det inkluderar företagets identifieringnummer. Den här ändringen hjälper till att garantera att företagets identifieringnummer visas på ett försäljningskvittot. Alternativt kan du kan lägga till företagets identifieringnummer på försäljningskvittot i fritt format.

### <a name="set-up-functionality-profiles"></a>Ställa in funktionsprofiler

Ställa in kassafunktionsprofiler:

- På snabbfliken **Inleveransnumrering** ställer du in inleveransnumrering genom att skapa eller uppdatera poster för transaktionstyperna **Försäljning**, **Försäljningsorder** och **Retur**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Konfigurera anpassade fält så att de kan användas i kvittoformat för försäljningskvitton

Du kan konfigurera språktext och anpassade fält som används i kassakvittoformat. Standardföretaget för den användare som skapar kvittoinställningen bör vara samma juridiska person där språktextinställningarna skapas. Du kan också skapa samma språktexter i både användarens standardföretag och den juridiska personen i butiken som installationen har skapats för.

På sidan **Språktext** kan du lägga till följande poster för etiketterna för de anpassade fälten för kvittolayout. Observera att värdena **Språk-ID**, **Text-ID** och **Text** som visas i tabellen bara är exempel. Du kan ändra dem för att uppfylla dina krav. Värdena för **text-ID** som du använder måste dock vara unika och de måste vara lika med eller större än 900001.

Lägg till följande kassaetiketter i avsnittet **kassa** på sidan **språktext** från tabellen.

| Språk-ID | Text-ID | Text                      |
|-------------|---------|---------------------------|
| en-US       | 900001  | QR-kod                   |
| en-US       | 900002  | Kontinuerligt nummer         |
| en-US       | 900003  | Detaljhandelsutskriftskod     |
| en-US       | 900004  | Totalt (försäljning)             |
| en-US       | 900005  | Total moms (försäljning)         |
| en-US       | 900006  | Total inkludera moms (försäljning) |
| en-US       | 900007  | Momsbelopp för försäljning        |
| en-US       | 900008  | Momsgrupp (försäljning)         |

På sidan **Anpassade fält** kan du lägga till följande poster för anpassade fält för kvittolayouter. Observera att värdena **Text-ID för rubrik** måste motsvara de värden för **Text-ID** som du angav på sidan **språktext**:

| Namn                 | Typ    | Text-ID för rubrik |
|----------------------|---------|-----------------|
| QRCODE               | Inleverans | 900001          |
| CONTINUOUSNUMBER     | Inleverans | 900002          |
| RETAILPRINTCODE      | Inleverans | 900003          |
| SALESTOTAL           | Inleverans | 900004          |
| SALESTOTALTAX        | Inleverans | 900005          |
| SALESTOTALINCLUDETAX | Inleverans | 900006          |
| SALESTAXAMOUNT       | Inleverans | 900007          |
| SALESTAXBASIS        | Inleverans | 900008          |

> [!NOTE]
> Det är viktigt att du anger rätt anpassade fältnamn, så som listas i föregående register. Om fel anpassat fältnamn saknas data i kvittona.

### <a name="configure-receipt-formats"></a>Konfigurera kvittoformat

För varje kvittoformat som krävs, ändra värdet för fältet **Utskriftssätt** till **Skriv alltid ut**.

I Layoutdesigner för kvitto, lägg till följande anpassade fält i lämpliga kvittoavdelningar. Observera att fältnamn motsvarar de språktexter som du definierade i föregående avsnitt.

- **Rubrik:** Lägg till följande fält:

    - Fälten **Butiksnamn** och **momsidentifieringsnummer** som används för att skriva ut företagsnamnet och identitetnumret på kvitton. Alternativt kan du kan lägga till företagsnamn och identitetsnummer på layouten i fritt format.
    - Fälten **Butiksadress**, **datum**, **Tid, 24 h**, **kvittonummer**, och **registreringsnummer**.
    - Fälten **Kontinuerligt nummer** för att identifiera numret på kontanttransaktionen i skatteregistreringstjänsten.

- **Rader:** Lägg till följande fält:

    - **Artikelnamn**.
    - **Antal**.
    - **Totalpris inkl. moms**.
    - **Momskod för butiksutskrift**, som används för att skriva ut den förkortade kod som motsvarar den momskod som gäller för varan.

- **Sidfot:** Lägg till följande fält:

    - Betalningsfält så att betalningsbeloppen för varje betalningsmetod skrivs ut. Till exempel fältet **Namn på betalningsmedel** och **Belopp för betalningsmedel** till en rad i layouten.
    - Fältgruppen **Total försäljning**:

        - Fältet **Total (försäljning)**, som används för att skriva ut kvittots totala kontanta försäljningsbelopp. Beloppet är exklusive skatt. Förskottsbetalningar och presentkortsoperationer exkluderas.
        - Fältet **Totalt inklusive moms (försäljning)**, som används för att skriva ut kvittots totala kontanta försäljningsbelopp. Beloppet är inklusive skatt. Förskottsbetalningar och presentkortsoperationer exkluderas.
        - Fältet **Totalt inklusive moms (försäljning)**, som används för att skriva ut kvittots totala kontanta försäljningsbelopp. Förskottsbetalningar och presentkortsoperationer exkluderas.

    - Fältgruppen **Momsuppdelning**. Alla fält i den här fältgruppen måste skrivas ut på en separat rad.

        - Fältet **Moms-Id**, vilket är ett standardfält som gör att en momsöversikt kan skrivas ut för varje momskod. Fältet måste läggas till på en ny rad.
        - Fältet **Momsprocent**, som är ett standardfält som används för att skriva ut momssatsen för momskoden.
        - Fältet **Momsgrupp (försäljning)**, som används för skriva ut kvittots totala kontanta försäljningsbelopp för momskoden. Förskottsbetalningar och presentkortsoperationer exkluderas.
        - Fältet **Momsbelopp (försäljning)**, som används för skriva ut kvittots momsbelopp för kontantförsäljning för momskoden.
        - Fältet **Momskod för butiksutskrift**, som används för att skriva ut den förkortade kod som motsvarar den momskod.

    - Fält **QR-kod**, som används för att skriva ut referensen till den registrerade kontanttransaktionen i form av QR-kod.

        > [!NOTE]
        > Värdet **QR-kod** hämtas från räkenskapsregistersvaret. EFR returnerar bara en QR-kod i sina svar om värdet i fältet **Attribut** i EFR-konfigurationen beskrivs i EFSTA-dokumentationen. QR-kodformatet i fältet **Attribut** i ER-konfigurationen måste ställas in på **BMP**.

Mer information om hur du arbetar med kvittoformat finns i [Ställ in och designa inleveransformat](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-austria"></a>Ställ in räkenskapsintegration för Österrike

Exemplet på integrering av räkenskapsregistreringstjänsten för Österrike baseras på [räkenskapsintegrationsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\Efr** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (till exempel [i version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). Proven [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) av en leverantör av skattedokument, vilket är ett filnamnstillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [ställa in ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md). 

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare (VM) i Microsoft Dynamics Lifecycle Services (LCS). Mer information finns i [Implementeringsriktlinjer för det skattemässiga integreringsexemplet för Österrike (äldre)](emea-aut-fi-sample-sdk.md). Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

Slutför konfigurationsstegen för räkenskapsintegration som beskrivs i [ställa in räkenskapsintegration för Commerce-kanaler](setting-up-fiscal-integration-for-retail-channel.md):

1. [Ställa in process för räkenskapsregistrering](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Var noga med att notera inställningarna för den process för räkenskapsregistrering som är [specifika för det här exemplet på skatteregistreringstjänsten](#set-up-the-registration-process).
1. [Ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Aktivera manuell körning av uppskjutna räkenskapsregistreringar](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Konfigurera kanalkomponenter](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Ställa in registrationsprocessen

Om du vill aktivera registreringsprocessen, följ dessa steg för att ställa in Commerce-administration. Mer information om [Ställ in räkenskapsintegrering för handelskanaler](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Ladda ner konfigurationsfiler för leverantören av skattedokument och skatteanslutningen:

    1. Öppna [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen.
    1. Välj en korrekt version av frisläppningen enligt din SDK/programversion (till exempel **[frisläppning/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Öppna **src \> FiscalIntegration \> Efr**.
    1. Öppna **Konfigurationer \> DocumentProviders** och hämta konfigurationsfilerna för: **DocumentProviderFiscalEFRSampleAustria.xml** och **DocumentProviderNonFiscalEFRSampleAustria.xml** (till exempel, [platsen för filerna för utgivning/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders)).
    1. Ladda ner konfigurationsfilen för räkenskapskoppling på **Konfigurationer \> Anslutningar \> ConnectorEFRSample.xml** (till exempel [filen för versionen/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Konfigurationsfilerna för det här exemplet för skatteintegration finns i följande mappar i Retail SDK på en utvecklar-VM i LCS:
    >
    > - **Konfigurationsfiler för finansiell dokumentleverantör:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration
    > - **Konfigurationsfil för räkenskapskoppling:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration
    > 
    > Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> delade Commerce-parametrar**. På fliken **allmänt** anger du alternativet **Aktivera räkenskapsintegration** till **Ja**.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegration \> Leverantörer av skattedokument** och läs in konfigurationsfiler för skattedokumentleverantören som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegration \> Räkenskapskopplingar** och läs in konfigurationsfilen för räkenskapskoppling för skattedokumentleverantören som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Funktionsprofiler för koppling**. Skapa två nya funktionsprofiler en för varje finansiell dokumentleverantör som du laddade tidigare, och välj den skatteanslutna anslutningen som du laddade tidigare. Uppdatera [datamappningsinställningarna](#default-data-mapping) efter behov.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Tekniska profiler för koppling**. Skapa en ny teknisk profil för koppling och välj räkenskapskoppling som du laddade tidigare. Uppdatera [kopplingsinställningarna](#fiscal-connector-settings) efter behov.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Grupper för skattekoppling**. Skapa två nya skatteanslutningsgrupper, en för varje funktionsprofil för anslutningsprogram som du skapade tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Processer för räkenskapsregistrering**. Skapa en ny räkenskapsregistrering och två steg för räkenskapsregistrering och välj de grupper för räkenskapskoppling som du skapade tidigare.
1. Gå till **Retail and Commerce \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**. Välj en funktionsprofil som är kopplad till butiken där registreringsprocessen ska aktiveras. På snabbfliken **Process för räkenskapsregistrering**, välj räkenskapsregistreringsprocessen som du skapade tidigare. För att möjliggöra registrering av icke-fiskala händelser på kassan, på snabbflikarna **Funktioner**, under **Kassa** ange alternativet **Granska** till **Ja**.
1. Gåt ill **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Kassaprofiler \> Maskinvaruprofiler**. Välj en maskinvaruprofil som är länkad till den Hardware Station som kvittoskrivare ska anslutas till. På snabbfliken **Kringutrustning för räkenskaper**, välj teknisk profil för koppling som du skapade tidigare.
1. Öppna distributionstidsplanen (**Retail och Commerce \> Retail och Commerce-IT \> Distributionsschema**) och välj jobb **1070** och **1090** för att överföra data till kanaldatabasen.

#### <a name="default-data-mapping"></a>Standarddatamappning

Följande standarddatamappning ingår i konfigurationen av leverantören av skattedokument som tillhandahålls som en del av exemplet på räkenskapsintegration.

- **Mappning av momssats** – Mappning av procentvärden för moms som har ställts in för momskoderna till värden i attributet **TaxG** (momsgrupp) i förfrågningar som skickas till skattetjänsten. Här är standardmappningen:

    ```
    A: 20.00; B: 10.00; C: 13.00; D: 0.00; E: 19.00; F: 7.00
    ```

    Den första komponenten i varje par representerar en momsgrupp som stöds av EFR-räkenskapsregistreringstjänsten. Den andra komponenten motsvarar momssatsen. Mer information om momsgrupper som EFR stöder för Österrike finns i [EFR-referensen](https://public.efsta.net/efr/).

#### <a name="fiscal-connector-settings"></a>Inställningar för räkenskapskoppling

Följande inställningar ingår i den skatteanslutningskonfiguration som tillhandahålls som en del av det skattemässiga integrationsexemplet:

- **Slutpunktsadress** – URL:en för skatteregistreringstjänsten.
- **Enhetens tidsgräns** – hur länge, i millisekunder, som räkenskapskoppling väntar på ett svar från räkenskapsregistreringstjänst.
- **Visa meddelanden för skatteregistreringar** – Den här flaggan styr om meddelanden som skatteregistreringstjänsten returnerar ska visas för operatorn.

### <a name="configure-channel-components"></a>Konfigurera kanalkomponenter

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Mer information finns i [Implementeringsriktlinjer för det skattemässiga integreringsexemplet för Österrike (äldre)](emea-aut-fi-sample-sdk.md).
>
> Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

#### <a name="set-up-the-development-environment"></a>Konfigurera en utvecklingsmiljö

Följ dessa steg för att ställa in en utvecklingsmiljö för att testa och utöka provet.

1. Eller hämta [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions)-databasen. Välj en korrekt version av frisläppningen enligt din SDK/programversion. För mer information, se [Hämta Retail SDK-exempel och referenspaket från GitHub och NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Öppna EFR-lösningen på **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln** och bygg den.
1. Installera CRT-tillägg:

    1. Sök efter CRT installationsprogram:

        - **Commerce Scale Unit:** I mappen **Efr\\ScaleUnit\\ScaleUnit.EFR.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **ScaleUnit.EFR.Installer**.
        - **Lokal CRT i Modern POS:** I mappen **Efr\\ModernPOS\\ModernPOS.EFR.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **ModernPOS.EFR.Installer**.

    1. Starta CRT installationsprogrammet för filnamnstillägget från kommandorad:

        - **Commerce Scale Unit.**

            ```Console
            ScaleUnit.EFR.Installer.exe install --verbosity 0
            ```

        - **Lokal CRT på Modern POS:**

            ```Console
            ModernPOS.EFR.Installer.exe install --verbosity 0
            ```

1. Install tilläggen för Hardware Station:

    1. Lokal i mappen **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461**, hitta installationsprogrammet **HardwareStation.EFR.Installer**.
    1. Starta installationsprogrammet för filnamnstillägget från kommandorad.

        ```Console
        HardwareStation.EFR.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Produktionsmiljö

Följ stegen i [Konfigurera en byggpipeline för ett skatteintegrationsprov](fiscal-integration-sample-build-pipeline.md) för att generera och släppa Cloud Scale Unit och självbetjäningsdistributionspaket för skatteintegreringsexemplet. Mall **EFR build-pipeline.yml** YAML-filen finns i **Pipeline\\YAML_Files** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Design av tilläggen

Exemplet på integrering av räkenskapsregistreringstjänsten för Österrike baseras på [räkenskapsintegrationsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\Efr** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (till exempel [i version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). Proven [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) av en leverantör av skattedokument, vilket är ett filnamnstillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [ställa in ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md). 

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Mer information finns i [Implementeringsriktlinjer för det skattemässiga integreringsexemplet för Österrike (äldre)](emea-aut-fi-sample-sdk.md). Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

### <a name="commerce-runtime-extension-design"></a>Utbyggbarhetdesign för Commerce Runtime

Syftet med tillägget som är en skattedokument leverantör är att generera tjänstspecifika dokument och hantera svar från räkenskapsregistreringstjänsten.

#### <a name="request-handler"></a>Begärandehanterare

Det finns två anförfrågningshanterare för dokumentleverantörer:

- **DocumentProviderEFRFiscalAUT** – Den här hanteraren används för att generera skattedokument för räkenskapsregistreringstjänst.
- **DocumentProviderEFRNonFiscalAUT** – Den här hanteraren används för att generera icke-skattedokument för räkenskapsregistreringstjänst.

Dessa hanterare ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Commerce-administration.

Kopplingen stöder följande begäranden:

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett tjänstspecifikt dokument som ska registreras i räkenskapsregistreringstjänst.
- **GetNonFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket icke-skattedokument som ska skapas. Den returnerar ett tjänstspecifikt dokument som ska registreras i räkenskapsregistreringstjänst.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på. För närvarande stöds följande händelser: försäljning, utskrift av X-rapport, utskrift av Z-rapport, insättning på kundkonto, insättning av kundorder, verifieringshändelser och icke-försäljningstransaktioner.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Denna begäran returnerar svaret från skatteregistreringstjänsten. Svaret serialiseras så att det går att spara.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilerna för leverantören av skattedokument finns i mappen **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders** mappen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen:

- **DocumentProviderFiscalEFRSampleAustria** – Konfigurationsfilen för skattedokumentleverantören för skattedokument.
- **DocumentProviderNonFiscalEFRSampleAustria** – Konfigurationsfilen för skattedokumentleverantören för icke skattedokument.

Syftet med den här filen är att aktivera inställningar för skattedokumentprovidern som ska konfigureras från Commerce-administration. Filformatet justeras med kraven för konfiguration av räkenskapsintegration.

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget som är en räkenskapskoppling är att kommunicera med räkenskapsregistreringstjänsten. Hardware Station tillägg använder HTTP-protokollet för att skicka dokument som CRT-tillägget genererar till räkenskapsregistreringstjänsten. Den hanterar också svar som tas emot från räkenskapsregistreringstjänsten.

#### <a name="request-handler"></a>Begärandehanterare

**EFRHandler** begäranhanteraren är startpunkten för hantering av begäranden till räkenskapsregistreringstjänst.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Commerce-administration.

Räkenskapskopplingen stöder följande begäranden:

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till räkenskapsregistreringstjänsten och returnerar ett svar från den.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av tjänsten för räkenskapsregistrering.
- **InitializeFiscalDeviceRequest** – den här begäran används för initiera tjänsten för räkenskapsregistrering.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av anslutningsprogram på **src\\FiscalIntegration\\Efr\\konfigurationer\\anslutningsprogram\\ConnectorEFRSample.xml** i [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen. Syftet med filen är att aktivera inställningar för räkenskapskoppling som ska konfigureras från Commerce-administration. Filformatet justeras med kraven för konfiguration av räkenskapsintegration.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
