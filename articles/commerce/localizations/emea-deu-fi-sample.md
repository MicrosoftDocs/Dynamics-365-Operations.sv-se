---
title: Exempel på skatteregistreringstjänsten för Tyskland
description: I det här avsnittet finns en översikt över exemplet på räkenskapsintegration för Tyskland i Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-5-29
ms.openlocfilehash: ca747215a8dfb85237365880ad5bdd49e57ec949
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944698"
---
# <a name="fiscal-registration-service-integration-sample-for-germany"></a>Exempel på skatteregistreringstjänsten för Tyskland

[!include[banner](../includes/banner.md)]

I det här avsnittet finns en översikt över exemplet på räkenskapsintegration för Tyskland i Microsoft Dynamics 365 Commerce.

För att uppfylla lokala räkenskapskrav för kassaregister i Tyskland Microsoft Dynamics 365 Commerce funktionaliteten för Tyskland inkluderar ett exempel på integration av kassan (POS) med en extern skatteregistreringstjänst. Det här exemplet utökar [funktionen räkenskapsintegrering](fiscal-integration-for-retail-channel.md). Den är baserad på [EFR (elektroniskt skatteregister)](https://www.efsta.eu/de/fiskalloesungen/deutschland) lösningar från [EFSTA](https://www.efsta.eu/de/) och möjliggör kommunikation med EFR-tjänsten via HTTPS-protokollet. EFR-tjänsten bör ha en värd för antingen Retail Hardware eller en separat dator som kan kopplas till från maskinvarutjänsten. Exemplet tillhandahålls i form av källkod och är en del av Retail Software Development Kit (SDK).

Microsoft släpper inte någon maskinvara, programvara eller dokumentation från EFSTA. För information om hur du får EFR-lösning och använder den, kontakta [EFSTA](https://www.efsta.eu/de/kontakt/kontakt).

## <a name="scenarios"></a>Scenarier

Följande scenarier täcks av integrationsexempel för skatteregistreringstjänster för Tyskland:

### <a name="sales-operations"></a>Försäljningsåtgärder

- **Registrering av hämtköp och returer i skatteregistreringstjänsten:**

    Registrering av försäljningsoperationer inkluderar följande steg:

    1. Registrering av transaktionens start

        Början på varje transaktion registreras i ett TSE (tekniskt säkerhetselement) som är anslutet till EFR-tjänsten. Efter registrering tilldelar en TSE ett transaktions-ID (TID).

    2. Registrering av transaktionens slut.

        När en transaktion avslutas i kassan registreras den genom att använda samma TID som tilldelades vid registreringen av transaktionsstarten. Då skickas detaljerade transaktionsdata till skatteregistreringstjänsten. Dessa data inkluderar försäljningsradinformation och information om rabatter, betalningar och skatter.

    3. Få ett svar från skatteregistreringstjänsten

        Säkerhetsdata tas emot från en TSE som en del av ett svar och sparas i transaktionen i kanaldatabasen. Säkerhetsdata består av följande information:

        - TID
        - Datum och starttid för transaktionens start
        - Datum och starttid för transaktionens slut
        - Signaturräknare
        - Kontrollvärde
        - Serienummer för TSE

- **Registrering av kundorder i skatteregistreringstjänsten:** Registreringsprocessen är densamma som processen för kontanta och föra med försäljningar och returer.
- **Registrering av verksamhet som innebär presentkort och insättningar:** Registreringsprocessen är densamma som processen för kontanta och föra med försäljningar och returer.

#### <a name="notifying-users-about-fiscal-registration-failures"></a>Meddela användare om misslyckade skatteregistreringar

Det finns två sätt att skatteregistreringstjänsten kan meddela användarna om fel som inträffade under räkenskapsregistreringen:

- Skriv ut ytterligare information från svaret i fältet **Infomeddelande** på kvitton.
- Visa meddelanden från räkenskapstjänsten som användarmeddelanden i kassan.

    > [!NOTE]
    > Den här meddelandemekanismen kräver att parametern **Visa meddelanden för skatteregistrering** på sidan **Tekniska profiler för koppling** aktiveras.

#### <a name="printing-receipts"></a>Skriver ut kvitton

Kvittoutskrift är obligatoriskt i Tyskland. Alla inleveranser måste minst innehålla följande information:

- Namn och adress på det aktuella företaget
- Information om varor, inklusive deras priser och kvantiteter
- Information om mottagna betalningar
- Information om skatter, inklusive totala belopp per momssats
- Säkerhetsdata:

    - TID
    - Datum och starttid för transaktionens start
    - Datum och starttid för transaktionens slut
    - Signaturräknare
    - Kontrollvärde
    - Serienummer för TSE

- Informationsmeddelande

> [!NOTE]
> En QR-kod kan också skrivas ut på kvitton. Även om QR-koden är valfri rekommenderas den. För mer information om hur du får QR-kod som en del av ett svar från skatteregistreringstjänsten, se "EFR-guiden \[DE\]" dokument som publiceras på webbplatsen för [EFSTA-dokumentationen](https://public.efsta.net/efr/).
>
> Fältet **Infomeddelande** på kvitton visar ett meddelande från skatteregistreringstjänsten. Om till exempel en signaturenhet bryts, kan specialtext skrivas ut på ett kvitto.

#### <a name="voided-suspended-and-recalled-transactions"></a>Annullerade, uppskjutna och återkallade transaktioner

- En annullerad transaktion registreras som en begäran om att avsluta en transaktion i skatteregistreringstjänsten.
- En uppskjuten transaktion registreras som en begäran om att avsluta en transaktion i skatteregistreringstjänsten.
- En återkallad transaktion registreras som en början på en ny transaktion i skatteregistreringstjänsten.

### <a name="non-sales-transactions-and-shift-closing"></a>Icke-försäljningstransaktioner och skiftstängning

Följande icke-försäljningstransaktioner registreras som icke-skattemässiga operationer i skatteregistreringstjänsten genom att använda **NFS**-taggen: 

- Stäm av startbelopp
- Växelpost
- Borttagning av betalningsmedel
- Lämna pengar i kassaskåp
- Bankinsättning
- Intäktskonton
- Utgiftskonton

Åtgärden **Stäng skift** registreras också som icke-skattemässig operation i skatteregistreringstjänsten genom att använda **NFS**-taggen.

### <a name="data-export-and-audit"></a>Export och granskning av data

Alla transaktioner måste signeras av en TSE för att säkerställa deras integritet, äkthet och fullständighet, och för att förhindra manipulering av registrerade data.

> [!WARNING]
> Endast en certifierad TSE kan användas. Mer information om typerna och modellerna för TSE som stöds i EFR-lösningen finns i dokumentet "EFR guide \[DE\]" som publiceras på webbplatsen för [EFSTA-dokumentation](https://public.efsta.net/efr/). Mer information om hur du väljer och får en TSE kontaktar du [EFSTA](https://www.efsta.eu/at/kontakt).

I Tyskland krävs stöd för DSFinV-K-exporten. DSFinV-K-exporten kan utlösas i EFR-lösningen. Mer information om DSFinV-K-exporten finns i dokumentet "EFR guide \[DE\]" som publiceras på webbplatsen för [EFSTA-dokumentationen](https://public.efsta.net/efr/).

### <a name="limitations-of-the-sample"></a>Begränsningar i provet

Räkenskapsregistreringstjänsten stöder bara scenarier där moms inkluderas i priser. Därför måste alternativet **Priser inkluderar moms** anges som **Ja** för både butiker och kunder.

Skattetjänsten stöder inte situationer där mer än en momskod används för samma transaktionsrad.

Ramverket för skatteintegrering har inte stöd för försäljningsofferter. Dessa operationer registreras därför inte i skattetjänsten.

## <a name="set-up-commerce-for-germany"></a>Ställa in Commerce för Tyskland

Det här avsnittet beskriver inställningar för Commerce som avser och rekommenderas för Tyskland. Mer information finns i [Startsida för Commerce](../index.md).

Om du vill använda funktionen för Tyskland måste du ange följande inställningar.

- I den primära adressen för den juridiska personen ställer du in **land/region** till **DEU** (Tyskland).
- I POS-funktionalitetsprofilen för varje butik som finns i Tyskland, ställ in **ISO-kod** till **DE** (Tyskland).

Du måste ange följande allmänna inställningar för Tyskland. Observera att du måste köra lämpliga distributionsjobb när du har slutfört inställningarna.

### <a name="set-up-vat-per-german-requirements"></a>Ställa in moms per tyskt krav

Du måste skapa momskoder, momsgrupper och artikelmomsgrupper. Du måste även ställa in momsinformation för produkter och tjänster. Mer information om hur du ställer in och använder moms finns i [Momsöversikt](../../finance/general-ledger/indirect-taxes-overview.md).

På försäljningsinleveranser kan du skriva ut en förkortad kod för en momskod (till exempel "A" eller "B"). Om du vill göra funktionen tillgänglig ställer du in fältet **Utskriftskod** på sidan **Momskoder**.

### <a name="set-up-stores"></a>Skapa butiker

På sidan **Alla butiker** uppdaterar du butiksinformation. Du måste speciellt ställa in följande parametrar:

- I fältet **Momsgrupp** anger du en momsgrupp som ska användas för försäljning till standardkund.
- Ange alternativet **Priserna inkluderar moms** till **Ja**.
- Ställ in fältet **Namn** på företagsnamnet. Den här ändringen hjälper till att garantera att företagsnamnet visas på ett försäljningskvittot. Alternativt kan du kan lägga till företagsnamnet på layouten av försäljningskvittot i fritt format.
- Ange fältet **Skatteidentifieringsnummer (TIN)** så att det inkluderar företagets identifieringnummer. Den här ändringen hjälper till att garantera att företagets identifieringnummer visas på ett försäljningskvittot. Alternativt kan du kan lägga till företagets identifieringnummer på försäljningskvittot i fritt format.

### <a name="set-up-functionality-profiles"></a>Ställa in funktionsprofiler

Ställa in kassafunktionsprofiler. På snabbfliken **Inleveransnumrering** ställer du in inleveransnumrering genom att skapa eller uppdatera poster för transaktionstyperna **Försäljning**, **Försäljningsorder** och **Retur**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Konfigurera anpassade fält så att de kan användas i kvittoformat för försäljningskvitton

Du kan konfigurera språktext och anpassade fält som används i kassakvittoformat. Standardföretaget för den användare som skapar kvittoinställningen bör vara samma juridiska person där språktextinställningarna skapas. Du kan också skapa samma språktexter i både användarens standardföretag och den juridiska personen i butiken som installationen har skapats för.

På sidan **Språktext** kan du lägga till följande poster för etiketterna för de anpassade fälten för kvittolayout. Observera att värdena **Språk-ID**, **Text-ID** och **Text** som visas i tabellen bara är exempel. Du kan ändra dem för att uppfylla dina krav. Värdena för **text-ID** som du använder måste dock vara unika och de måste vara lika med eller större än 900001.

Lägg till följande kassaetiketter i avsnittet **kassa** på sidan **språktext**.

| Språk-ID | Text-ID | Text                                  |
|-------------|---------|---------------------------------------|
| en-US       | 900001  | QR-kod                               |
| en-US       | 900002  | Transaktions-ID                        |
| en-US       | 900003  | Detaljhandelsutskriftskod                 |
| en-US       | 900004  | Momsbelopp för försäljning                    |
| en-US       | 900005  | Momsgrupp (försäljning)                     |
| en-US       | 900006  | Transaktionens startdatum/starttid           |
| en-US       | 900007  | Transaktionens slutdatum/sluttid             |
| en-US       | 900008  | Säkerhetselementets serienummer |
| en-US       | 900009  | Signaturräknare                     |
| en-US       | 900010  | Kontrollvärde                           |
| en-US       | 900011  | Infomeddelande                          |

På sidan **Anpassade fält** kan du lägga till följande poster för anpassade fält för kvittolayouter. Observera att värdena **Text-ID för rubrik** måste motsvara de värden för **Text-ID** som du angav på sidan **språktext**.

| Namn                            | Typ    | Text-ID för rubrik |
|---------------------------------|---------|-----------------|
| QRCODE\_DE                      | Inleverans | 900001          |
| TRANSACTIONID\_DE               | Inleverans | 900002          |
| RETAILPRINTCODE\_DE             | Inleverans | 900003          |
| SALESTAXAMOUNT\_DE              | Inleverans | 900004          |
| SALESTAXBASIS\_DE               | Inleverans | 900005          |
| TRANSACTIONSTARTDATETIME\_DE    | Inleverans | 900006          |
| TRANSACTIONENDDATETIME\_DE      | Inleverans | 900007          |
| SECURITYELEMENTSERIALNUMBER\_DE | Inleverans | 900008          |
| SIGNCOUNTER\_DE                 | Inleverans | 900009          |
| SIGN\_DE                        | Inleverans | 900010          |
| INFOMESSAGE\_DE                 | Inleverans | 900011          |

> [!NOTE]
> Det är viktigt att du anger rätt anpassade fältnamn, så som listas i föregående register. Om fel anpassat fältnamn saknas data i kvittona.

### <a name="configure-receipt-formats"></a>Konfigurera kvittoformat

För varje kvittoformat som krävs, ändra värdet för fältet **Utskriftssätt** till **Skriv alltid ut**.

I Layoutdesigner för kvitto, lägg till följande anpassade fält i lämpliga kvittoavdelningar. Observera att fältnamn motsvarar de språktexter som du definierade i föregående avsnitt.

- **Rubrik:** Lägg till följande fält:

    - Fälten **Butiksnamn** och **momsidentifieringsnummer** som används för att skriva ut företagsnamnet och identitetsnumret på kvitton. Alternativt kan du kan lägga till företagsnamn och identitetsnummer på layouten i fritt format.
    - Fälten **Butiksadress**, **datum**, **Tid, 24 h**, **kvittonummer**, och **registreringsnummer**.

- **Rader:** Lägg till följande fält:

    - Fältet **Artikelnamn**
    - Fältet **Kvt**
    - Fältet **Totalpris inkl. moms**
    - Fältet **Momskod för butiksutskrift**, som används för att skriva ut den förkortade kod som motsvarar den momskod som gäller för varan.

- **Sidfot:** Lägg till följande fält:

    - Betalningsfält så att betalningsbeloppen för varje betalningsmetod skrivs ut. Till exempel fältet **Namn på betalningsmedel** och **Belopp för betalningsmedel** till en rad i layouten.
    - Fält i fältgruppen **Momsuppdelning**. Alla fält i den här fältgruppen måste skrivas ut på en separat rad.

        - Fältet **Moms-Id**, vilket är ett standardfält som gör att en momsöversikt kan skrivas ut för varje momskod. Fältet måste läggas till på en ny rad.
        - Fältet **Momsprocent**, som är ett standardfält som används för att skriva ut momssatsen för momskoden.
        - Fältet **Momsgrupp (försäljning)**, som används för skriva ut kvittots totala kontanta försäljningsbelopp för momskoden. Förskottsbetalningar och presentkortsoperationer exkluderas.
        - Fältet **Momsbelopp (försäljning)**, som används för skriva ut kvittots momsbelopp för kontantförsäljning för momskoden.
        - Fältet **Momskod för butiksutskrift**, som används för att skriva ut den förkortade kod som motsvarar den momskod.

    - Fält som innehåller skyddade transaktionsdata som returneras av skatteregistreringstjänsten:

        - Fältet **Transaktions-ID** som identifierar numret på kontanttransaktionen i skatteregistreringstjänsten
        - Fältet **Transaktionens startdatum tid**
        - Fältet **Transaktionens slutdatum tid**
        - Fältet **Säkerhetselementets serienummer**
        - Fältet **Signaturräknare**
        - Fältet **Kontrollvärde**
        - Fält **QR-kod**, som används för att skriva ut referensen till den registrerade kontanttransaktionen i form av QR-kod

        > [!NOTE]
        > Värdet **QR-kod** hämtas från räkenskapsregistersvaret. EFR returnerar bara en QR-kod i sina svar om värdet i fältet **Attribut** i EFR-konfigurationen beskrivs i EFSTA-dokumentationen. QR-kodformatet i fältet **Attribut** i ER-konfigurationen måste ställas in på **BMP**.

    - Fältet **Infomeddelande** så att aviseringsmeddelanden från skatteregistreringstjänsten kan visas på kvitton. Om till exempel en signaturenhet bryts, kan specialtext skrivas ut på ett kvitto.

Mer information om hur du arbetar med kvittoformat finns i [Ställ in och designa inleveransformat](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-germany"></a>Ställ in räkenskapsintegration för Tyskland

Exemplet på integrering av räkenskapsregistreringstjänsten för Tyskland baseras på [räkenskapsintegrationsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\Efr** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (till exempel [i version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). Proven [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) av en leverantör av skattedokument, vilket är ett filnamnstillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [ställa in ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md). 

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare (VM) i Microsoft Dynamics Lifecycle Services (LCS). Mer information finns i [Implementeringsriktlinjer för det skattemässiga integreringsexemplet för Tyskland (äldre)](emea-deu-fi-sample-sdk.md).
>
> Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

Slutför konfigurationsstegen för räkenskapsintegration som beskrivs i [ställa in räkenskapsintegration för Commerce-kanaler](setting-up-fiscal-integration-for-retail-channel.md):

1. [Ställa in process för räkenskapsregistrering](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Var noga med att notera inställningarna för den process för räkenskapsregistrering som är [specifika för det här exemplet på skatteregistreringstjänsten](#set-up-the-registration-process).
1. [Ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

    > [!WARNING]
    > Felhanteringsfunktionerna i ramverket för skatteintegrering kanske inte stämmer överens med de lokala skattereglerna.
    >
    > - Vi rekommenderar att du lämnar alternativet **Fortsätt vid fel** på sidan **Skatteregistreringsprocess** avaktiverat eftersom alla transaktioner måste registreras korrekt, även om det första försöket med skatteregistrering inte lyckades.
    > - Innan du aktiverar alternativet **Hoppa över** eller **Markera som registrerad** på sidan **Skatteregistreringsprocess** bör du diskutera ändringarna i skatteregistreringsprocessen med din skattekonsult eller det lokala skattekontoret.

1. [Aktivera manuell körning av uppskjutna räkenskapsregistreringar](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Konfigurera kanalkomponenter](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Ställa in registrationsprocessen

Om du vill aktivera registreringsprocessen, följ dessa steg för att ställa in Commerce-administration. Mer information om [Ställ in räkenskapsintegrering för handelskanaler](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Ladda ner konfigurationsfiler för leverantören av skattedokument och skatteanslutningen:

    1. Öppna [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen.
    1. Välj en korrekt version av frisläppningen enligt din SDK/programversion (till exempel **[frisläppning/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Öppna **src \> FiscalIntegration \> Efr**.
    1. Ladda ner konfigurationsfilen för finansiell dokumentleverantör på **Konfigurationer \> DocumentProviders \> DocumentProviderFiscalEFRSampleGermany.xml** (t.ex. [filen för version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders/DocumentProviderFiscalEFRSampleGermany.xml)).
    1. Ladda ner konfigurationsfilen för räkenskapskoppling på **Konfigurationer \> Anslutningar \> ConnectorEFRSample.xml** (till exempel [filen för versionen/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Konfigurationsfilerna för det här exemplet för skatteintegration finns i följande mappar i Retail SDK på en utvecklar-VM i LCS:
    >
    > - **Konfigurationsfilen för räkenskapsdokumentprovidern:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleGermany.xml
    > - **Konfigurationsfil för räkenskapskoppling:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration\\ConnectorEFRSample.xml
    > 
    > Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> delade Commerce-parametrar**. På fliken **allmänt** anger du alternativet **Aktivera räkenskapsintegration** till **Ja**.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegration \> Leverantörer av skattedokument** och läs in konfigurationsfilen för skattedokumentleverantören som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegration \> Räkenskapskopplingar** och läs in konfigurationsfilen för räkenskapskoppling för skattedokumentleverantören som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Funktionsprofiler för koppling**. Skapa en ny funktionsprofil för anslutning. Välj dokumentleverantören och den koppling som du läst in tidigare. Uppdatera [datamappningsinställningarna](#default-data-mapping) efter behov.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Tekniska profiler för koppling**. Skapa en ny teknisk profil för koppling och välj räkenskapskoppling som du laddade tidigare. Uppdatera [kopplingsinställningarna](#fiscal-connector-settings) efter behov.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Grupper för skattekoppling**. Skapa en ny grupp för räkenskapskoppling för den funktionsprofil för koppling som du skapade tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegration \> Processer för räkenskapsregistrering**. Skapa en ny räkenskapsregistrering och räkenskapsregistrering och välj den grupp för räkenskapskoppling som du skapade tidigare.
1. Gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**. Välj en funktionsprofil som är kopplad till butiken där registreringsprocessen ska aktiveras. På snabbfliken **Process för räkenskapsregistrering**, välj räkenskapsregistreringsprocessen som du skapade tidigare.
1. Gåt ill **Retail och Commerce \> Kanalinställningar \> Kassainställning \> Kassaprofiler \> Maskinvaruprofiler**. Välj en maskinvaruprofil som är länkad till den Hardware Station som kvittoskrivare ska anslutas till. På snabbfliken **Kringutrustning för räkenskaper**, välj teknisk profil för koppling som du skapade tidigare.
1. Öppna distributionstidsplanen (**Retail och Commerce \> Retail och Commerce-IT \> Distributionsschema**) och välj jobb **1070** och **1090** för att överföra data till kanaldatabasen.

#### <a name="default-data-mapping"></a>Standarddatamappning

Följande standarddatamappning ingår i konfigurationen av leverantören av skattedokument som tillhandahålls som en del av exemplet på räkenskapsintegration.

- **Mappning av betalningsmedelstyp** – Mappningen av betalningsmetoder till värden i attributet **PayG** (betalningsgrupp) i begäran som skickas till räkenskapstjänsten. Här är standardmappningen:

    ```
    1: 0; 2: 1; 3: 3; 4: 8; 5: 2; 6: 0; 7: 7; 8: 6; 9: 0; 10: 8; 11: 1
    ```

    Den första komponenten i varje par representerar en betalningsmetod som ställts in för butiken. Den andra komponenten representerar motsvarande betalningsgrupp som stöds av EFR-räkenskapsregistreringstjänsten. Mer information om betalningsgrupper som EFR stöder för Tyskland finns i [EFR-referensen](https://public.efsta.net/efr/).

    Exempelmappningen av betalningsmetoder motsvarar butiksbetalningsmetoderna som konfigureras i standarddemodata.

    | Betalningsmetod | Namn på betalningsmetod |
    |----------------|---------------------|
    | 1              | Kontanter                |
    | 2              | Kontroll               |
    | 3              | Kort                |
    | 4              | Kundkonto    |
    | 5              | Övriga               |
    | 6              | Valuta            |
    | 7              | Verifikation             |
    | 8              | Presentkort           |
    | 9              | Betalningsmedelborttagning/växelkassa |
    | 10             | Förmånskort       |
    | 11             | Ej lokala checkar    |

    Du måste ändra exempelmappningen enligt betalningsmetoderna som är konfigurerade i programmet.

- **Inkludera kunddata** – Om den här parametern är aktiverad kommer begäranden till skattetjänsten att innehålla kundinformation, som namn och adresser, i fall där en kund läggs till i en transaktion.
- **Mappning av momssats** – Mappning av procentvärden för moms som har ställts in för momskoderna till värden i attributet **TaxG** (momsgrupp) i förfrågningar som skickas till skattetjänsten. Här är standardmappningen:

    ```
    A: 19.00; B: 7.00; C: 10.70; D: 5.50; E: 0.00
    ```

    Den första komponenten i varje par representerar en momsgrupp som stöds av EFR-räkenskapsregistreringstjänsten. Den andra komponenten motsvarar momssatsen. Mer information om momsgrupper som EFR stöder för Tyskland finns i [EFR-referensen](https://public.efsta.net/efr/).

- **Momsgrupp för presentkort och insättningar** – Värdet av attributet **TaxG** i förfrågningar som skickas till räkenskapstjänsten, baserat på operationer som innefattar presentkort eller insättningar. Här är standardmappningen:

    ```
    G
    ```

- **Momsgrupp för momsregistrering** – Värdet av attributet **TaxG** i begäran som skickas till räkenskapstjänsten, baserat på operationer som är momsbefriade. Här är standardmappningen:

    ```
    F
    ```

> [!NOTE]
> Momsinställningarna i standarddatamappningen ansvarar för matchning av momsinställningar i systemet och momsgrupperna i EFR-tjänsten. Momsgrupper kan endast skrivas ut på inleveranser om fältet **Kod för utskrift** har ställts in på sidan **Momskoder**.

#### <a name="fiscal-connector-settings"></a>Inställningar för räkenskapskoppling

Följande inställningar ingår i den skatteanslutningskonfiguration som tillhandahålls som en del av det skattemässiga integrationsexemplet:

- **Slutpunktsadress** – URL:en för skatteregistreringstjänsten.
- **Timeout** – hur länge, i millisekunder, som räkenskapskoppling väntar på ett svar från räkenskapsregistreringstjänst.
- **Visa meddelanden för skatteregistreringar** – Den här flaggan styr om meddelanden som skatteregistreringstjänsten returnerar ska visas för operatorn.

### <a name="configure-channel-components"></a>Konfigurera kanalkomponenter

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Mer information finns i [Implementeringsriktlinjer för det skattemässiga integreringsexemplet för Tyskland (äldre)](emea-deu-fi-sample-sdk.md).
>
> Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

#### <a name="set-up-the-development-environment"></a>Konfigurera en utvecklingsmiljö

Följ dessa steg för att ställa in en utvecklingsmiljö för att testa och utöka provet.

1. Eller hämta [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions)-databasen. Välj en korrekt version av frisläppningen enligt din SDK/programversion. För mer information, se [Hämta Retail SDK-exempel och referenspaket från GitHub och NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Öppna EFR-lösningen på **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln** och bygg den.
1. Installera Commerce Runtime tillägg:

    1. Sök efter CRT installationsprogram:

        - **Commerce Scale Unit:** I mappen **Efr\\ScaleUnit\\ScaleUnit.EFR.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **ScaleUnit.EFR.Installer**.
        - **Lokal CRT i Modern POS:** I mappen **Efr\\ModernPOS\\ModernPOS.EFR.Installer\\bin\\Debug\\net461** hitta installationsprogrammet **ModernPOS.EFR.Installer**.

    1. Starta CRT installationsprogrammet för filnamnstillägget från kommandorad:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EFR.Installer.exe install --verbosity 0
            ```

        - **Lokal CRT på Modern POS:**

            ```Console
            ModernPOS.EFR.Installer.exe install --verbosity 0
            ```

1. Install tilläggen för Hardware Station:

    - Lokal i mappen **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461**, hitta installationsprogrammet **HardwareStation.EFR.Installer**.
    - Starta installationsprogrammet för filnamnstillägget från kommandorad:

        ```Console
        HardwareStation.EFR.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Produktionsmiljö

Följ stegen i [Konfigurera en byggpipeline för ett skatteintegrationsprov](fiscal-integration-sample-build-pipeline.md) för att generera och släppa Cloud Scale Unit och självbetjäningsdistributionspaket för skatteintegreringsexemplet. Mall **EFR build-pipeline.yml** YAML-filen finns i **Pipeline\\YAML_Files** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Design av tilläggen

Exemplet på integrering av räkenskapsregistreringstjänsten för Tyskland baseras på [räkenskapsintegrationsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\Efr** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (till exempel [i version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). Proven [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) av en leverantör av skattedokument, vilket är ett filnamnstillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [ställa in ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md). 

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Mer information finns i [Implementeringsriktlinjer för det skattemässiga integreringsexemplet för Tyskland (äldre)](emea-deu-fi-sample-sdk.md). Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

### <a name="crt-extension-design"></a>CRT tilläggsdesign

Syftet med tillägget som är en skattedokument leverantör är att generera tjänstspecifika dokument och hantera svar från räkenskapsregistreringstjänsten.

#### <a name="request-handler"></a>Begärandehanterare

Det finns en begäranhanterare för dokumentleverantören **DocumentProviderEFRFiscalDEU**. Den här hanteraren används för att generera skattedokument för räkenskapsregistreringstjänst. Den ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Commerce-administration.

Kopplingen stöder följande begäranden:

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett tjänstspecifikt dokument som ska registreras i räkenskapsregistreringstjänst.
- **GetFiscalTransactionExtendedDataDocumentProviderRequest** – Denna begäran returnerar svaret tillsammans med utökade data.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av skattedokument finns på **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleGermany.xml** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Syftet med den här filen är att aktivera inställningar för skattedokumentprovidern som ska konfigureras från Commerce-administration. Filformatet justeras med kraven för konfiguration av räkenskapsintegration.

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget som är en räkenskapskoppling är att kommunicera med räkenskapsregistreringstjänsten.

Hardware Station-tillägget **HardwareStation.Extension.EFRSample**. Den använder HTTP-protokollet för att skicka dokument som CRT-tillägget genererar till räkenskapsregistreringstjänsten. Den hanterar också svar som tas emot från räkenskapsregistreringstjänsten.

#### <a name="request-handler"></a>Begärandehanterare

**EFRHandler** begäranhanteraren är startpunkten för hantering av begäranden till räkenskapsregistreringstjänst. Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Commerce-administration.

Kopplingen stöder följande begäranden:

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till räkenskapsregistreringstjänsten och returnerar ett svar från den.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av tjänsten för räkenskapsregistrering.
- **InitializeFiscalDeviceRequest** – den här begäran används för initiera tjänsten för räkenskapsregistrering.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av anslutningsprogram på **src\\FiscalIntegration\\Efr\\konfigurationer\\anslutningsprogram\\ConnectorEFRSample.xml** i [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen. Syftet med filen är att aktivera inställningar för räkenskapskoppling som ska konfigureras från Commerce-administration. Filformatet justeras med kraven för konfiguration av räkenskapsintegration.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
