---
title: Exempel på integrering av kvittoskrivare för Italien
description: I denna artikel finns en översikt över exemplet på räkenskapsintegrering för Italien i Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-11-01
ms.openlocfilehash: e63f8d68b8b79143771c0b1c757cb78659183b67
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280279"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Exempel på integrering av kvittoskrivare för Italien

[!include[banner](../includes/banner.md)]

I denna artikel finns en översikt över exemplet på räkenskapsintegrering för Italien i Microsoft Dynamics 365 Commerce.

Commerce-funktionen för Italien omfattar en exempelintegrering av kassan (POS) med en kvittoskrivare. Provet förlänger [räkenskapsintegreringsfunktionen](fiscal-integration-for-retail-channel.md) så att det fungerar med [Epson FP-90III serier](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) skrivare från Epson och det möjliggör kommunikation med en kvittoskrivare i webbserverläget via webbtjänsten EpsonFPMate med Fiscal ePOS-Print API. Proven stöder bara läget Registratore Telemato (RT). Exemplet tillhandahålls i form av källkod och är en del av Retail Software Development Kit (SDK).

Microsoft släpper inte någon maskinvara, programvara eller dokumentation från Epson. Om du vill ha information om hur du får kvittoskrivaren och använder den kan du kontakta [Epson Italia S.p.A](https://www.epson.it).

## <a name="scenarios"></a>Scenarier

Följande scenarier täcks av integreringsexempel för kvittoskrivare för Italien:

- Försäljningsscenarier:

    - Skriv ut ett skatteinleverans för kontantbetalningsförsäljning och hämtköp och returer.
    - Hämta ett svar från kvittoskrivaren och lagra det i kanaldatabasen.
    - Skatter:

        - Mappa till kvittoskrivarens momskoder (avdelningar).
        - Överför mappade skattedata till kvittoskrivaren.
        - Skriv ut moms på en skatteinleverans.

    - Betalningar.

        - Mappa till kvittoskrivarens betalningsmetoder.
        - Skriv ut betalning på en skatteinleverans.
        - Skriv ut ändringsinformation.

    - Skriv ut radrabatter.
    - Presentkort:

        - Uteslut en utfärdad/omdebiterad presentkortsrad från ett skattekvitto för en försäljning.
        - Skriv ut en betalning där ett presentkort används som vanlig betalningsmetod.

    - Skriv ut räkenskapskvitton för åtgärder inom kundorder:

        - Ett skattekvitto skrivs inte ut för en kundorderdeposition.
        - Skriv ut en skattekvitto för leveransrader i en kundorder.
        - Skriv ut ett skattekvitto för upphämtningen av en kundorder.
        - Skriv ut en skatteinleverans för en returorder.

    - Skriv ut en streckkod för kvittonumret på ett skattekvitto.
    - Skriv ut [kundinformation](emea-ita-customer-information.md) som har angetts för en försäljningstransaktion på en skatteinleverans. Ett exempel på denna information är kundens kod. 

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
- Skriv ut beloppet för den tidigare betalade insättningen på ett skattekvitto för en upphämtningsåtgärd för kundorder.
- Dra av insättningsbeloppet för kundordern från betalningsrader när en kundorder skapas.
- Spara beräknade justeringar av betalningsrader i kanaldatabasen med en referens för en hybrid kundorder.

### <a name="limitations-of-the-sample"></a>Begränsningar i provet

- kvittoskrivaren stöder bara scenarier där moms inkluderas i priset. Därför måste alternativet **Inkludera moms** anges som **Ja** för både butiker och kunder.
- Dagliga rapporter (räkenskapsårets X och räkenskapsårets Z) skrivs ut med det format som är inbäddat i räkenskapsskrivarens dator.
- kvittoskrivaren har inte stöd för blandade transaktioner. Alternativet **Förbjud att blanda försäljning och returer i ett kvitto** bör anges till **Ja** i kassafunktionsprofiler.
- Exemplet stöder bara integrering med en kvittoskrivare som arbetar i läget Registratore Telemato (RT).

## <a name="set-up-fiscal-integration-for-italy"></a>Ställ in räkenskapsintegrering för Italien

Exemplet på integrering av kvittoskrivaren för Italien baseras på [räkenskapsintegreringsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\EpsonFP90IIISample** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (t.ex. [the sample in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). Proven [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) av en leverantör av skattedokument, vilket är ett tillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [konfigurera ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md).

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare (VM) i Microsoft Dynamics Lifecycle Services (LCS). Mer information finns i [Implementeringsriktlinjer för det skattemässiga skrivarintegreringsexemplet för Italien (äldre)](emea-ita-fpi-sample-sdk.md).
>
> Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

Slutför konfigurationsstegen för räkenskapsintegrering som beskrivs i [konfigurera räkenskapsintegrering för Commerce-kanaler](setting-up-fiscal-integration-for-retail-channel.md).

1. [Ställa in process för räkenskapsregistrering](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Var noga med att notera inställningarna för den process för räkenskapsregistrering som är [specifika för det här kvittoskrivare integrering av prov](#set-up-the-registration-process).
1. [Ställ in räkenskapstexter för rabatter](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).
1. [Ange inställningar för felhantering](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Ställ in räkenskapsrapporter X/Y från POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Aktivera manuell körning av uppskjutna räkenskapsregistreringar](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Ställ in funktionerna för hantering av kundinformation i kassa](emea-ita-customer-information.md#setup).
1. [Konfigurera kanalkomponenter](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Ställa in registrationsprocessen

Om du vill aktivera registreringsprocessen, följ dessa steg för att konfigurera Commerce headquarters. Mer information om [Ställ in räkenskapsintegrering för handelskanaler](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Ladda ner konfigurationsfiler för providern av skattedokument och skatteanslutningen:

    1. Öppna [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen.
    1. Välj en korrekt version av frisläppningen enligt din SDK/programversion (till exempel **[frisläppning/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Öppna **src \> FiscalIntegration \> EpsonFP90IIISample**.
    1. Hämta konfigurationsfilen för räkenskapsdokumentprovidern på **CommerceRuntime \> DocumentProvider.EpsonFP90IIISample \> Configuration \> DocumentProviderEpsonFP90IIISample.xml** (t.ex. [filen för version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/CommerceRuntime/DocumentProvider.EpsonFP90IIISample/Configuration/DocumentProviderEpsonFP90IIISample.xml)).
    1. Ladda ner konfigurationsfilen för räkenskapskoppling på **HardwareStation \> EpsonFP90IIIFiscalDeviceSample \> konfiguration \> ConnectorEpsonFP90IIISample.xml** (t.ex. [filen för version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/HardwareStation/EpsonFP90IIIFiscalDeviceSample/Configuration/ConnectorEpsonFP90IIISample.xml).

    > [!WARNING]
    > På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Konfigurationsfilerna för det här exemplet för skatteintegrering finns i följande mappar i Retail SDK på en utvecklar-VM i LCS:
    >
    > - **Konfigurationsfilen för räkenskapsdokumentprovidern** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml
    > - **Konfigurationsfil för räkenskapskoppling:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml
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

- **Mappning av betalningsmedelstyp** – Mappningen av betalningsmetoder som har konfigurerats för butiken till betalningstyper som kvittoskrivaren har stöd för. Följande exempel visar standardmappningen.

    ```JSON
    {"PaymentMethods": [
        {"StorePaymentMethod":"1", "PrinterPaymentType":"0", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"3", "PrinterPaymentType":"2", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"4", "PrinterPaymentType":"2", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"6", "PrinterPaymentType":"0", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"8", "PrinterPaymentType":"6", "PrinterPaymentIndex":"01"}
        ],
        "DepositPaymentMethod": {"PrinterPaymentType":"2", "PrinterPaymentIndex":"00"}}
    ```

    Här följer en förklaring av attribut i den här mappningen:

    - **StorePaymentMethod** är en betalningsmetod som har ställts in för butiken på **Retail och Commerce \> Kanalinställningar \> Betalningsmetoder \> Betalningsmetoder**.
    - **PrinterPaymentType** och **PrinterPaymentIndex** är motsvarande betalningstyp och index som definieras i Epsons skatteskrivardokumentation.
    - **DepositPaymentMethod** används för att ange en skrivares betalningstyp och index för den del av kundorderupphämtningsbeloppet som kvittas med kundens orderdeposition.

    Följande tabell visar hur exempelmappningen av betalningsmetoder motsvarar butiksbetalningsmetoderna som konfigureras i standarddemodata.

    | Betalningsmetod | Namn på betalningsmetod |
    |----------------|---------------------|
    | 1              | Kontanter                |
    | 3              | Kort                |
    | 4              | Kundkonto    |
    | 6              | Valuta            |
    | 8              | Presentkort           |

    Du måste ändra exempelmappningen enligt betalningsmetoderna som är konfigurerade i programmet.

- **Streckkodstyp för kvittonummer** – Den typ av streckkod som används för att visa ett kvittonummer på ett skattekvitto. Standardmappningen är **CODE128**.
- **Skriv ut räkenskapsdata i kvittohuvudet** – Om den här parametern aktiveras skrivs butiksinformation ut på kvittot för räkenskapsåret. Den här informationen inkluderar butikens namn, adress och skatte-ID samt kassörens namn.
- **Mappning av kvittoskrivare** – Mappning av avdelningar på kvittoskrivaren till momssatser, momsbefriade typer och produkttyper. Följande exempel visar standardmappningen.

    ```JSON
    {"Departments": [
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"01"},
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"02"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"03"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"04"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"05"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"06"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"07"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"08"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"09"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"10"},
        {"VATRate":"0000", "VATExemptNature":"NS", "ProductType":"0", "DepartmentNumber":"99"}]}
    ```

    Här följer en förklaring av attribut i den här mappningen:

    - **VATRate** är en momssats som stöds och är konfigurerad som en momskod. Värdet i mappningen har två decimaler men ingen decimalavgränsare. Till exempel representerar **2200** representerar 22 procent och **1000** representerar 10 procent.
    - **VATExemptNature** används bara i fall där momssatsen är 0 (noll), vilket inkluderar fall där det inte finns någon moms. För närvarande stöds **VATExemptNature** bara för presentkort och värdet i mappningen bör motsvara värdet på egenskapen **VATExemptNatureForGiftCard** i XML-konfigurationsfilen.
    - **ProductType** är produkttypen. Värdet **0** representerar varor och värdet **1** representerar tjänster.
    - **DepartmentNumber** är numret på avdelningen som har konfigurerats på skrivaren och som motsvarar de tre föregående attributen.

    Du måste ändra exempelmappningen i enlighet med de momssatser som har konfigurerats i programmet och motsvarande avdelningar som har konfigurerats i kvittoskrivaren.

- **Momsbefriad natur för presentkort** – Den momsbefriade karaktär som ska tillämpas när ett presentkort utfärdas eller fylls på. Värdet ska motsvara någon post i avdelningsmappningen för kvittoskrivaren. Standardmappningen är **NS**.
- **Aktivera gratisartiklar** – Om den här parametern är aktiverad är den speciella *omaggio* rabattjusteringstypen för artiklar som har en 100-procents rabatt aktiverad.
- **Infokod för retur ursprung** – Infokoden som används för att samla in ursprunget för en returtransaktion om inget ursprungligt försäljningskvitto anges. Den här parametern används tillsammans med parametrarna **Infokod för originalförsäljningsdatum** och **Returnera ursprungskartläggning** för att generera ett korrekt meddelande i skattekvittot om ursprunget för en returtransaktion om ingen ursprungliga försäljningstransaktion existerar. 

    Denna infokod ska konfigureras så att användaren kan välja eller ange en av de möjliga returerna från butikerna. Den kan till exempel konfigureras som en lista med delkoder (till exempel **Retur från webbplatsen** eller **Retur from kiosk**). Parametern **Returnera ursprungsmappning** används sedan för att översätta värdet för infokoden till ett kommando för kvittoskrivaren.

    Den infokod som väljs för **Infokod för retur ursprung** bör konfigureras som en obligatorisk infokod som aktiveras en gång per försäljningstransaktion. Den ska tilldelas som infokoden **Returnerad produkt** i funktionsprofilen för kassan så att den förser **returprodukten** med åtgärden som körs.

    Inget standardvärde har angetts för den här mappningen. Du måste välja en infokod som är konfigurerad i ditt program.

- **Infokod för originalförsäljningsdatum** – Infokoden som används för att samla in ursprunget för originalförsäljningsdatum om inget ursprungligt försäljningskvitto anges. Den här parametern används tillsammans med parametrarna **Infokod för retur ursprung** och **Returnera ursprungskartläggning** för att generera ett korrekt meddelande i skattekvittot om ursprunget för en returtransaktion om ingen ursprungliga försäljningstransaktion existerar.

    Infokoden ska konfigureras så att fältet **Inmatningstyp** ställs in på **Datum**. Det ska konfigureras som en obligatorisk infokod som används en gång per försäljningstransaktion. Det bör också tilldelas som **Länkad infokod** för infokoden som är vald för **Infokod för returursprung** så att de två infokoderna avfyras en efter en.

    Inget standardvärde har angetts för den här mappningen. Du måste välja en infokod som är konfigurerad i ditt program.

- **Returnera ursprungsmappning** – Mappning av returursprung som används för att skriva ut ursprunget för en returtransaktion om inget ursprungligt försäljningskvitto anges. Den här parametern används tillsammans med parametrarna **Infokod för retur ursprung** och **Infokod för originalförsäljningsdatum** för att generera ett korrekt meddelande i skattekvittot om ursprunget för en returtransaktion om ingen ursprungliga försäljningstransaktion existerar. Följande exempel visar standardmappningen.

    ```JSON
    {"ReturnOrigins": [
        {"ReturnOrigin":"1", "PrinterReturnOrigin":"POS"},
        {"ReturnOrigin":"2", "PrinterReturnOrigin":"ND"}
        ],
        "PrinterReturnOriginWithoutFiscalData":"POS"}
    ```

    Här följer en förklaring av attribut i den här mappningen:

    - **ReturnOrigin** är ett av de möjliga ursprungen till returerna i butikerna. Värdet bör motsvara värdet för parametern **infokod för returursprung**.
    - **PrinterReturnOrigin** är ett av returkällorna som kvittoskrivaren accepterar (**POS**, **VR** eller **ND**).
    - **PrinterReturnOriginWithoutFiscalData** är returursprunget som skattetryckaren accepterar och som motsvarar en returtransaktion som är kopplad till en ursprunglig försäljningstransaktion som inte har kopplade skattedata, eftersom den inte registrerades via en skattetryckare. I detta fall identifieras det ursprungliga försäljningsdatumet som datumet för den ursprungliga försäljningstransaktionen.

Följande standarddatamappningar är föråldrade och hålls endast för bakåtkompatibel:

- Mappning av momskoder
- Betalningstyp för insättning

#### <a name="fiscal-connector-settings"></a>Inställningar för räkenskapskoppling

Följande inställningar ingår i den skatteanslutningskonfiguration som tillhandahålls som en del av det skattemässiga integreringsexemplet:

- **Slutpunktsadress** – Skrivarens URL.
- **Datum- och tidssynkronisering** – Ett värde som anger om datum och tid för skrivaren måste synkroniseras med den anslutna maskinvaran.

### <a name="configure-channel-components"></a>Konfigurera kanalkomponenter

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Mer information finns i [Implementeringsriktlinjer för det skattemässiga skrivarintegreringsexemplet för Italien (äldre)](emea-ita-fpi-sample-sdk.md).
>
> Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

#### <a name="set-up-the-development-environment"></a>Konfigurera en utvecklingsmiljö

Följ dessa steg för att konfigurera en utvecklingsmiljö för att testa och utöka provet.

1. Eller hämta [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions)-databasen. Välj en korrekt version av frisläppningen enligt din SDK/programversion. För mer information, se [Hämta Retail SDK-exempel och referenspaket från GitHub och NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Öppna integreringslösningen för kvittoskrivaren på **Dynamics365Commerce.Solutions\\FiscalIntegration\\EpsonFP90IIISample\\EpsonFP90IIISample.sln** och skapa det.
1. Installera CRT-tillägg:

    1. Sök efter CRT installationsprogram:

        - **Commerce Scale Unit:** I mappen **EpsonFP90IIISample\\ScaleUnit\\ScaleUnit.EpsonFP90III.Installer\\bin\\Debug\\net461** hitta **ScaleUnit.EpsonFP90III.Installer** installationsprogrammet.
        - **Lokal CRT på Modern POS:** I mappen **EpsonFP90IIISample\\ModernPOS\\ModernPOS.EpsonFP90III.Installer\\bin\\Debug\\net461**, hitta **ModernPOS.EpsonFP90III.Installer** installationsprogrammet.

    1. Starta CRT installationsprogrammet för filnamnstillägget från kommandorad:

        - **Commerce Scale Unit.**

            ```Console
            ScaleUnit.EpsonFP90III.Installer.exe install --verbosity 0
            ```

        - **Lokal CRT på Modern POS:**

            ```Console
            ModernPOS.EpsonFP90III.Installer.exe install --verbosity 0
            ```

1. Install tilläggen för Hardware Station:

    1. I **EpsonFP90IIISample\\HardwareStation\\HardwareStation.EpsonFP90III.Installer\\bin\\Debug\\net461** mappen, hitta **HardwareStation.EpsonFP90III.Installer** installationsprogrammet.
    1. Starta installationsprogrammet för filnamnstillägget från kommandorad:

        ```Console
        HardwareStation.EpsonFP90III.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Produktionsmiljö

Följ stegen i [Konfigurera en byggpipeline för ett skatteintegreringsprov](fiscal-integration-sample-build-pipeline.md) för att generera och släppa Cloud Scale Unit och självbetjäningsdistributionspaket för skatteintegreringsexemplet. Mall **EpsonFP90III build-pipeline.yml** YAML-filen finns i **Pipeline\\YAML_Files** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Design av tilläggen

Exemplet på integrering av kvittoskrivaren för Italien baseras på [räkenskapsintegreringsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\EpsonFP90IIISample** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (t.ex. [the sample in release/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). Proven [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) av en leverantör av skattedokument, vilket är ett tillägg för Commerce Runtime (CRT) och en skattekontakt, som är en förlängning av Commerce Hardware Station. Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [konfigurera ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md).

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för detta skatteintegreringsprov. Du måste använda föregående version av Retail SDK på en virtuell utvecklare i LCS. Mer information finns i [Implementeringsriktlinjer för det skattemässiga skrivarintegreringsexemplet för Italien (äldre)](emea-ita-fpi-sample-sdk.md). Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

### <a name="commerce-runtime-extension-design"></a>Utbyggbarhetdesign för Commerce Runtime

Syftet med tillägget som är en skattedokument leverantör är att generera utskriftspecifika dokument och hantera svar från räkenskapsregistreringsutskrift.

#### <a name="request-handler"></a>Begärandehanterare

**DocumentProviderEpsonFP90III** begäranhanteraren är ingångspunkten för begäran om att generera dokument från kvittoskrivaren.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Commerce headquarters.

Kopplingen stöder följande begäranden:

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett utskriftsspecifikt dokument som ska registreras i kvittoskrivaren.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på. För närvarande stöds följande händelser: försäljning, utskrift av X-rapport och utskrift av Z-rapport.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av skattedokument finns på **src\\FiscalIntegration\\EpsonFP90IIISample\\CommerceRuntime\\DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml** i databasen [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Syftet med den här filen är att aktivera inställningar för dokumentprovidern som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering.

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget som är en räkenskapskoppling är att kommunicera med kvittoskrivare. Tillägg HTTP-protokollet för att skicka dokument som CRT-tillägget genererar till kvittoskrivare. Den hanterar också svar som tas emot från kvittoskrivare.

#### <a name="request-handler"></a>Begärandehanterare

**EpsonFP90IIISample** begäranhanteraren är startpunkten för hantering av begäranden till kringutrustning för räkenskaper.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Commerce headquarters.

Kopplingen stöder följande begäranden:

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till skrivare och returnerar svaret från kvittoskrivaren.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av enheten.
- **InitializeFiscalDeviceRequest** – Denna begäran används för skrivarinitiering.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen för leverantör av anslutningsprogram på **src\\FiscalIntegration\\EpsonFP90IIISample\\HardwareStation\\EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml** i [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen. Syftet med filen är att aktivera inställningar för anslutningsprogram som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
