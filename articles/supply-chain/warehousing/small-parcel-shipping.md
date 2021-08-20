---
title: Leverans av små paket
description: Det här ämnet innehåller information om funktionen leverans av små paket (SPS). Med denna funktion kan Microsoft Dynamics 365 Supply Chain Management skicka uppgifter om en förpackad behållare till transportföretaget och sedan ta emot en leveransetikett, basleveranstariff och spårningsnummer tillbaka från det transportföretaget.
author: Mirzaab
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: e4682674e6f61b9b75276df57afa522b29b5f052fd8a4c450c7fcfbe79654f90
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780468"
---
# <a name="small-parcel-shipping"></a>Leverans av små paket

[!include [banner](../../includes/banner.md)]

Funktionen leverans av små paket (SPS) gör att Microsoft Dynamics 365 Supply Chain Management kan kommunicera direkt med transportföretag genom att tillhandahålla ett ramverk för kommunikation via transportföretags-API:er. Den här funktionen är användbar när du levererar enskilda försäljningsorder via kommersiella transportföretag i stället för att använda leverans av behållare eller LTL-leverans (mindre än lastbilslasten).

SPS-funktionen kommunicerar med transportföretaget via en dedikerad *tariffmotor*. Din organisation måste utveckla den här tariffmotorn i samverkan med transportföretaget eller transportnavtjänsten. Med tariffmotorn kan Supply Chain Management skicka uppgifter om en förpackad behållare till transportföretaget och sedan ta emot en leveransetikett, basleveranstariff och spårningsnummer tillbaka från det transportföretaget.

Leveranskostnaden som returneras läggs till på den associerade försäljningsordern som ett tillägg. Leveransetiketten som returneras kan sedan skrivas ut automatiskt med hjälp av en ZPL-skrivare (Zebra Programming Language) och tillämpas på försändelsen. Transportföretaget skannar den här leveransetiketten när han eller hon hämtar paketen på ditt lagerställe.

## <a name="prepare-your-system-to-support-sps"></a>Förbereda ditt system för stöd för SPS

Innan du kan börja använda SPS-funktionen måste du aktivera SPS-funktionen i Funktionshantering, lägga till din tariffmotor och ställa in modulerna **Transporthantering** och **Lagerstyrning** för att stödja den.

### <a name="turn-on-the-sps-feature"></a>Aktivera SPS-funktion

Innan du kan använda SPS-funktionen måste den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Transporthantering*
- **Funktionsnamn:** *Leverans av små paket*

### <a name="deploy-and-set-up-rate-engines"></a>Distribuera och ställa in tariffmotor.

Supply Chain Management omfattar inte några tariffmotorer. Du måste erhålla eller skapa eventuella tariffmotor som du behöver och sedan lägga till dem i systemet. Microsoft tillhandahåller dock en demotariffmotor som du kan använda för att testa.

#### <a name="download-and-deploy-the-demo-rate-engine"></a>Hämta och distribuera demotariffmotorn

Följ dessa steg för att hämta demotariffmotorn.

1. I GitHub, hämta [dynamic-link library (DLL) för demotariffmotor](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).
1. I din Supply Chain Management-server, spara DLL i mappen **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.

#### <a name="create-and-deploy-functional-rate-engines"></a>Skapa och distribuera funktionella tariffmotorer.

Mer information om hur du skapar och distribuerar funktionella tariffmotorer så att de kan användas i en tillverknings- eller testmiljö finns i följande ämnen:

- [Skapa en ny transporthanteringsmotor](../transportation/create-new-transportation-management-engine.md)
- [Ställa in motorer för transporthantering](/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

Mer information om hur du skapar en SPS-tariffmotor finns i följande inlägg: [Leverans av små paket: Hur du använder funktionen för leverans av små paket i Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a>Ställa in en tariffmotor i Supply Chain Management

När du har skapat och distribuerat en tariffmotor för SPS följer du dessa steg och ställer in den.

1. Gå till **Transporthantering \> Inställningar \> Motorer \> Tariffmotor**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.
1. I den nya raden anger du följande fält:

    - **Tariffmotor** – Ange ett unikt namn för tariffmotorn. Om du använder demotariffmotorn anger du *demotariffmotor*.
    - **Namn** – Ange en kort beskrivning av tariffmotorn. Om du använder demotariffmotorn anger du *demotariffmotor*.
    - **ID på metadata för bedömning** – Välj det underlag som ska användas för att beräkna tariffen. Din tariff kan till exempel beräknas utifrån körsträcka. Om du använder demotariffmotorn kan du lämna det här fältet tomt.
    - **Montering av motor** – Ange filnamnet för DLL-paket som du distribuerade. Om du använder demotariffmotorn anger du *TMSSmallParcelShippingEngine.dll*.
    - **Motorklass** – Ange klassnamnet som har upprättats för din tariffmotor. Om du använder demotariffmotorn anger du *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.

## <a name="example-scenario"></a>Exempelscenario

I det här exempelscenariot visas hur du ställer in och använder SPS efter att du har förberett systemet enligt beskrivningen tidigare i det här avsnittet. I det här scenariot används den tidigare nämnda demotariffmotorn.

### <a name="make-demo-data-available"></a>Gör demodata tillgängliga

Om du vill arbeta genom detta scenario med hjälp av de demoposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

### <a name="set-up-the-scenario"></a>Ställ in scenario

I det här exemplet måste du ha ett demotransportföretag, en transportföretagsgrupp, en förpackningspolicy och en förpackningsprofil. Följande delgrupper förklarar hur du förbereder posterna som krävs för scenariot. I ett produktionsscenario liknar inställningsprocessen vanligtvis den process som beskrivs här. Du kommer dock att ställa in olika värden.

#### <a name="set-up-carriers"></a>Konfigurera transportföretag

Följ dessa steg för att ställa in ett transportföretag.

1. Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportföretag**.
1. I åtgärdsfönstret, välj **Ny** för att lägga till ett transportföretag.
1. I rubriken anger du följande värden:

    - **Transportföretag:** *Demotransportföretag*
    - **Namn:** *Demotransportföretag*
    - **Läge:** *Mark*

1. Ange följande värden på snabbfliken **Översikt**:

    - **Aktivera transportföretag:** *Ja*
    - **Aktivera värdering av transportföretag:** *Ja*

1. På snabbfliken **Tjänster** välj **Ny** för att lägga till en tjänst i rutnätet.
1. Ställ in följande värden för den nya tjänsten:

    - **Transportföretagstjänst:** *Demotransportföretagstjänst*
    - **Namn:** *Demotransportföretagstjänst*
    - **Transportmetod:** *Mark*

    Ange godtyckliga värden för alla andra fält efter behov. (När du sparar den nya transportföretagets post skapas ett nytt leveranssätt och fältet **Leveranssätt** ställs in automatiskt.)

1. På snabbfliken **Bedömningsprofiler** välj **Ny** för att lägga till skapa en bedömningsprofil till rutnätet.
1. Ställ in följande värden för den nya profilen:

    - **Bedömningsprofil:** *Demotransportföretagstjänst*
    - **Namn:** *Demotransportföretagstjänst*
    - **Tariffmotor:** *Demotariffmotor*

    Ange godtyckliga värden för alla andra fält efter behov.

1. Klicka på **Spara** i åtgärdsfönstret.

Mer information om hur du ställer in transportföretag hittar du på [Ställ in transportföretag](../transportation/tasks/set-up-shipping-carriers.md).

#### <a name="set-up-carrier-service-accounts"></a>Ställa in konton för transportföretag

Följ dessa steg för att ställa in ett konto för transportföretag.

1. Gå till **Transporthantering \> Inställningar \> Klassificering \> Konto för transportföretag**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till ett konto för transportföretag.
1. Ställ in följande värden för det nya kontot:

    - **Transportföretag:** *Demotransportföretag*
    - **Transportföretagstjänst:** *Demotransportföretagstjänst*
    - **Transportföretagets kundkontonummer:** Transportföretagets kundkontonummer som används för att verifiera och autentisera anslutningen till transportföretaget. Transportföretaget tillhandahåller detta värde. Om du använder demotjänsten kan du ange ett godtyckligt värde.
    - **Plats:** *6*
    - **Lagerställe:** *62*

    > [!NOTE]
    > Ofta är värdet **kundkontonummer för transportföretaget** det enda värde som krävs för att autentisera anslutningen. Om din transportföretag kräver fler autentiseringsparametrar bör din organisation anpassa den här sidan för att lägga till extra fält efter behov.

#### <a name="set-up-a-container-packing-policy"></a>Ställa in policy för packning av behållare

Följ dessa steg för att ställa in en policy för packning av behållare.

1. Om du inte redan har ställt in en ZPL-skrivardefinition, ska du använda appen Dokumentflödesagenten för att konfigurera det. Mer information finns i [översikten över utskrift av dokument och relaterade avsnitt](../../fin-ops-core/dev-itpro/analytics/print-documents.md).
1. Gå till **Lagerstyrning \> Inställningar \> Behållare \> Policyer för packning av behållare**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en policy för packning av behållare.
1. Ange följande värden i nya policyns rubrik:

    - **Förpackningspolicy för behållare:** *demopolicy för packning*
    - **Beskrivning:** Ange en beskrivning för policyn

1. Ange följande värden på snabbfliken **Översikt**:

    - **Lagerställe:** *62*
    - **Standardplats för slutgiltig leverans:** *Baydoor*
    - **Viktenhet:** *KG*
    - **Policyn för stängning av behållare:** *Automatiskt släpp*
    - **Policyn för stängning av behållare:** *Gör tillgänglig vid slutlig leveransplats*

1. Ange följande värden på snabbfliken **Behållarmanifest**:

    - **Automatisk stängning av behållare:** *Ja*
    - **Manifestkrav för behållare:** *Transporthantering*
    - **Skriv ut behållarinnehåll:** *Nej*

1. Ange följande värden på snabbfliken **Utskrift av transportföretagsetikett**:

    - **Skriv ut leveransetikett för behållare:** *Alltid*
    - **Skrivarnamn:** Namnet på den ZPL-skrivare som ska skriva ut leveransetiketter

#### <a name="set-up-a-packing-profile"></a>Ställa in en förpackningsprofil

Följ dessa steg för att skapa en förpackningsprofil.

1. Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Förpackningsprofiler**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en förpackningsprofil i rutnätet.
1. Ställ in följande värden för den nya profilen:

    - **Förpackningsprofil-ID:** *Demoförpackningsprofil*
    - **Beskrivning:** Ange en beskrivning för profilen
    - **Förpackningspolicy för behållare:** *demopolicy för packning*
    - **Läge för behållar-ID:** *Auto*
    - **Behållartyp:** *SmallBox*

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a>Ställ in en kund att använda SPS-transportföretaget

Följ dessa steg om du vill ställa in en kund så att den kan använda det transportföretag som du skapat.

1. Gå till **Leverantörsreskontra \> kunder \> Alla kunder**.
1. I rutnätet hittar och väljer du kund *US-027*.
1. I Åtgärdsfönstret, på fliken **Allmän**, i gruppen **Ställ in**, markerar du **Kundkonton för transportföretag**.
1. På sidan **Kundkonton för transportföretag** i åtgärdsfönstret väljer du **Ny** om du vill lägga till ett konto i rutnätet.
1. Ställ in följande värden för det nya kontot:

    - **Transportföretag:** *Demotransportföretag*
    - **Kundkontonummer för transportföretaget:** *12345* (Värdet är inte viktigt för detta scenario, men det refereras till i nästa avsnitt.)

### <a name="go-through-the-example-scenario"></a>Gå igenom exempelscenariot

När du har ställt in alla exempeldata enligt beskrivningen i det föregående avsnittet kan du gå igenom exempelscenariot.

#### <a name="create-a-sales-order-and-process-the-work"></a>Skapa en försäljningsorder och bearbeta arbetet

Följ dessa steg för att skapa en försäljningsorder.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj *US-027*.
1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. På snabbfliken **Försäljningsorderhuvud** ange fältet **Transportföretagets kundkontonummer** till det värde du valt för den här kunden tidigare (*12345*).
1. I området **försäljningsorderrad** lägg till en försäljningsrad och ställ in följande värden för den:

    - **Artikelnummer:** *A0002*
    - **Kvantitet:** *1*
    - **Plats:** *6*
    - **Lagerställe:** *62*

1. Växla till vyn **Rubrik**.
1. Ange följande värden på snabbfliken **Leverans**:

    - **Transportföretag:** *Demotransportföretag*
    - **Transportföretagstjänst:** *Demotransportföretagstjänst*

1. Växla tillbaka till vyn **Rader**. Om du uppmanas att uppdatera leveranssättet för försäljningsraderna väljer du **Ja**.
1. I imorådet **Försäljningsorderrader**, välj den orderrad som du har ställt in tidigare och välj sedan **Lager \> Reservation**.
1. På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.
1. Stäng sidan **Reservation** om du vill återgå till försäljningsordern.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    Arbete skapas för att flytta artiklar från plockplatsen till förpackningsstationen.

1. I avsnittet **försäljningsorderrad** välj **Lagerställe \> Leveransdetaljer**.
1. På sidan **leveransinformation** gör en notering av leverans-ID. Du behöver det när du förpackar försändelsen i förpackningsstationen.
1. Stäng sidan **leveransinformation** om du vill återgå till försäljningsordern.
1. Anteckna försäljningsordernumret och gå sedan till **Lagerstyrning \> Arbete \> Allt arbete**.
1. Använd försäljningsordernumret för att söka efter och välja det arbete som skapades för ordern.
1. I åtgärdsfönstret på fliken **Arbete** välj **Slutför arbete**.
1. På sidan **Arbetet slutförs** i fältet **Användar-ID** välj ett användar-ID. Sedan i åtgärdsfönstret, välj **Validera arbete**.
1. Om arbetet går igenom valideringen, välj **Slutför arbete** i åtgärdsfönstret.

    Arbetet markeras som slutfört för att simulera förflyttningen av artiklar till förpackningsstationen.

#### <a name="pack-the-shipment"></a>Förpacka leveransen

Följ dessa steg för att förpacka leveransen.

1. Gå till **Lagerstyrning \> Inställning \> Arbetare** och se till att ditt användarkonto är kopplat till ett arbetarkonto för lagerhantering.
1. Gå till **lagerstyrning \> plocka och skapa behållare \> packa**.
1. I dialogrutan **Välj packningsstation** ställ in följande värden:

    - **Plats:** *6*
    - **Lagerställe:** *62*
    - **Plats:** *Packa*
    - **Förpackningsprofil-ID:** *Demoförpackningsprofil*

1. Välj **OK**.
1. Sidan **Förpacka** visas. I ett produktionsscenario skannar arbetaren en licensinnehavare eller ett försändelse-ID. I det här scenariot öppnar du dock sidan **Alla leveranser** och söker efter leveransnumret för den leverans som du precis har skapat. Ange sedan detta värde i fältet **ID-nummer eller leverans** på sidan **Förpacka**. Du kan även ange det leverans-ID som du har gjort en anteckning av tidigare.
1. Klicka på **Ny behållare** i åtgärdsfönstret.
1. I dialogrutan som visas visas information om den nya behållaren. Lämna standardvärdena och välj sedan **OK**.
1. På sidan **Förpacka** på snabbfliken **Artikelpackning** i fältet **Identifierare**, välj *A0002* vill förpacka artikeln. Artikeln läggs till i behållaren.
1. I åtgärdsfönstret väljer du **Behållare för leverans**.

    Sidan **Behållare för leverans** som visas har en rad för den behållare som du just skapat. Däremot är fältet **Behållarmanifest-ID** i den raden tomt, eftersom du ännu inte har fått leveransetiketten och spårningsnumret från transportföretaget.

1. Klicka på **Stäng behållare** i åtgärdsfönstret.
1. I dialogrutan **Stäng behållare** ange fältet **Bruttovikt** till *1 kg* och välj **OK**.

    Leveransetiketten ska nu skrivas ut på den ZPL-skrivare som du valde tidigare. Det bör likna följande exempel:

    ![Exempel på frakthandling.](media/sps-label-example.png "Exempel på leveransetikett")

1. Observera att värdena **Behållarmanifest-ID** och **Total frakt** har lagts till som mottagna från transportföretaget.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]