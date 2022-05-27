---
title: Förpackningsstrategier för behållare
description: I det här avsnittet beskrivs skillnaderna mellan förpackningsstrategier för behållare, samt exempel.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab34cee7fd495ec26f6b20da2aa43895f49f677c
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676395"
---
# <a name="container-packing-strategies"></a>Förpackningsstrategier för behållare

[!include [banner](../includes/banner.md)]

En *förpackningsstrategi för behållare* är en strategi som du kan använda för att definiera artikelallokeringar mellan behållare. I det här avsnittet beskrivs skillnaderna mellan *förpacka i alla öppna behållare* och *förpacka i enbart aktuella behållare*.

- **Förpacka i alla öppna behållare** – Systemet måste kontrollera alla öppna behållare som redan har skapats under cykeln för skapande av behållare för att säkerställa att artikeln får plats i en av dem. Under förpackning kontrollerar systemet varje artikel för att avgöra om den får plats i någon av de tidigare skapade behållarna. Om artikeln inte får plats i en befintlig behållare skapas en ny behållare automatiskt och fortsätter tills den är färdig med att packa hela ordern.

    Till exempel, *n* beställda artiklar kräver skapande av behållare. I värsta fall, varje gång systemet behandlar ett objekt som inte passar i någon befintlig behållare, kommer det att göra totalt (\[(*n* – 1) × (*n* + 1)\] ÷ 2) kontrollerar för att utvärdera om artikeln passar in i befintliga behållare.

- **Packa endast till aktuell behållare** – Systemet måste endast kontrollera den senast skapade behållaren för att säkerställa att artikeln passar in i den. Under förpackning kontrollerar systemet varje artikel för att avgöra om den får plats i den senast skapade behållarna. Om artikeln inte får plats i den behållaren skapar systemet en ny behållare automatiskt och fortsätter tills den är färdig med att packa hela ordern.

    Till exempel, *n* beställda artiklar kräver skapande av behållare. I det aktuella fallet görs en total kontroll av artikeln (*n* – 1) för att bedöma om artikeln får plats i behållare.

## <a name="example-of-the-flow-for-container-packing-strategies"></a>Exempel på flödet för förpackningsstrategier för behållare

Du kan konfigurera följande artiklar för skapande av behållare.

| Artikel | Fysiska dimensioner (bredd × djup × höjd) | Vikt |
|---|---|---|
| HDMI-kabel 6' | 1 × 1 × 1 | 1 |
| HDMI-kabel 12' | 2 × 1 × 1 | 1 |
| HDMI-kabel 18' | 3 × 1 × 1 | 2 |

Du kan även ställa in följande låda som ska användas för förpackning.

| Behållare | Fysiska dimensioner (längd × bredd × höjd) | Vikt | Volym |
|---|---|---|---|
| Mellanlåda | 6 × 3 × 2 | 10 | 100 |

Slutligen ställer du in en order med följande produkter och kvantiteter.

| Försäljningsorderrad | Antal |
|---|---|
| HDMI-kabel 12' | 9 |
| HDMI-kabel 18' | 8 |
| HDMI-kabel 6' | 13 |

I följande tabell sammanfattas hur skapande av behållare fungerar när du använder *förpacka i alla öppna behållare* och när du använder strategin *förpacka endast i aktuell behållare*.

| Packa i alla öppna behållare | Packa i aktuell behållare |
|---|---|
| <p>HDMI-kabel 12':</p><ol><li>Skapa en ny behållare CONT0001.</li><li>Sätt 9 ea i behållare CONT001.</li></ol> | <p>HDMI-kabel 12':</p><ol><li>Skapa en ny behållare CONT0001.</li><li>Sätt 9 ea i behållare CONT001.</li></ol> |
| <p>HDMI-kabel 18':</p><ol><li>Kontrollera om artikeln får plats i behållaren CONT0001.</li><li>Skapa en ny behållare CONT0002.</li><li>Sätt 5 ea i behållare CONT0002.</li><li>Skapa en ny behållare CONT0003.</li><li>Sätt 3 ea i behållare CONT0003.</li></ol> | <p>HDMI-kabel 18':</p><ol><li>Kontrollera om artikeln får plats i behållaren CONT0001.</li><li>Skapa en ny behållare CONT0002.</li><li>Sätt 5 ea i behållare CONT0002.</li><li>Skapa en ny behållare CONT0003.</li><li>Sätt 3 ea i behållare CONT0003.</li></ol> |
| <p>HDMI-kabel 6':</p><ol><li>Kontrollera om artikeln får plats i behållaren CONT0001.</li><li>Sätt 1 ea i behållare CONT0001.</li><li>Kontrollera om artikeln får plats i behållaren CONT0002.</li><li>Kontrollera om artikeln får plats i behållaren CONT0003.</li><li>Sätt 4 ea i behållare CONT0003.</li><li>Skapa en ny behållare CONT0004.</li><li>Sätt 8 ea i behållare CONT0004.</li></ol> | <p>HDMI-kabel 6':</p><ol><li>Kontrollera om artikeln får plats i behållaren CONT0003.</li><li>Sätt 4 ea i behållare CONT0003.</li><li>Skapa en ny behållare CONT0004.</li><li>Sätt 9 ea i behållare CONT0004.</li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a>Exempelscenario: Packa enstaka order per behållare

Det här avsnittet innehåller ett scenario där systemet har ställts in för konsolidering av flera order till en försändelse. Därför sker skapande av behållare från försäljningsordern för att säkerställa att varje order som innehåller flera produkter förpackas i en egen behållare.

Med den här funktionen kan du hantera scenarier där du bara får packa en försäljningsorder i varje behållare, så att distributionscentret kan direktutlevera fullständiga behållare mellan butiker. Förutom butiksscenarier (order per butik och leverans till ett distributionscenter för direktutleverans) används den här metoden också för resurssnåla leveranskedjor (försäljningsorder per just-in-time-produktionsrad).

I det här scenariot visas hur du kan minska antalet behållare som utvärderas under förpackning med hjälp av *Förpacka endast i aktuell behållare* bara för att skapa behållare.

### <a name="prerequisites"></a>Förutsättningar

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a>Aktivera funktionen Konsolidera försändelser i systemet

I det här scenariot används funktionen *Konsolidera försändelser*. Om den funktionen inte redan är tillgänglig i systemet måste du aktivera den med hjälp av [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

#### <a name="make-demo-data-available"></a>Gör demodata tillgängliga

Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management. Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.

### <a name="inspect-or-create-container-types"></a>Inspektera eller skapa behållartyper

Om du vill inspektera dina behållartyper, eller om du behöver skapa nya behållartyper, följer du dessa steg.

1. Gå till **Warehouse management** \> **Inställningar** \> **Behållare** \> **Behållartyper**.
1. Se till att var och en av följande behållartyper är tillgänglig i dina demodata. Redigera eller skapa behållartyper efter behov.

    - Behållartyp 1:

        - **Behållartypkod:** *Kartong-stor*
        - **Beskrivning:** *Stor kartong*
        - **Högsta nettovikt:** *100*
        - **Volym:** *400*
        - **Längd:** *4*
        - **Bredd:** *10*
        - **Höjd:** *10*

    - Behållartyp 2:

        - **Behållartypkod:** *Kartong-Medel*
        - **Beskrivning:** *Medelstor kartong*
        - **Högsta nettovikt:** *50*
        - **Volym:** *200*
        - **Längd:** *2*
        - **Bredd:** *10*
        - **Höjd:** *10*

    - Behållartyp 3:

        - **Behållartypkod:** *Kartong-liten*
        - **Beskrivning:** *Liten kartong*
        - **Högsta nettovikt:** *20*
        - **Volym:** *100*
        - **Längd:** *1*
        - **Bredd:** *10*
        - **Höjd:** *10*

### <a name="inspect-or-create-container-groups"></a>Inspektera eller skapa behållargrupper

Om du vill inspektera dina behållargrupper, eller om du behöver skapa nya behållargrupper, följer du dessa steg.

1. Gå till **Warehouse management** \> **Inställningar** \> **Behållare** \> **Behållargrupper**.
1. Se till att var och en av följande behållargrupper är tillgänglig i dina demodata. Om den inte är tillgänglig väljer du **Ny** för att skapa den.

    - **Behållargrupp-ID:** *kartonger*
    - **Beskrivning:** *Kartongstorlekar*

1. I snabbfliken **Detaljer** för behållargrupp *Lådor* se till att följande rader finns. Om de inte har det markerar du **Ny** om du vill lägga till dem.

    - Rad 1:

        - **Löpnummer:** *1*
        - **Behållartyp:** *Kartong-stor*
        - **Utnyttjandegrad för fraktbehållare:** *100*

    - Rad 2:

        - **Löpnummer:** *2*
        - **Behållartyp:** *Kartong-Medel*
        - **Utnyttjandegrad för fraktbehållare:** *100*

    - Rad 3:

        - **Löpnummer:** *3*
        - **Behållartyp:** *Kartong-liten*
        - **Utnyttjandegrad för fraktbehållare:** *100*

### <a name="create-a-new-container-build-template"></a>Skapa en ny behållarversionsmall

Så här skapar du en ny behållarversionsmall:

1. Gå till **Warehouse management** \> **Inställningar** \> **Behållare** \> **Mall för behållarversion**.
1. Välj **Ny** om du vill skapa en behållarversionsmall med följande inställningar:

    - **Löpnummer:** *1*
    - **ID för behållarmall:** *kartong*
    - **Behållargrupp-ID:** *kartonger*
    - **Basfrågetyper:** *Försäljningsallokeringsrad*
    - **Kod för påfyllnadssteg:** *234*
    - **Tillåt delade plockningar:** *Ja*
    - **Förpackningsstrategi för behållare:** *Packa endast i aktuell behållare*
    - **Packa efter direktivenhet:** *Nej*

1. Medan raden för den nya mallen fortfarande är markerad väljer du **Redigera från** i åtgärdsfönstret.
1. En dialogruta för standard frågeredigeraren visas. På fliken **Sortera**, välj **Lägg till** en rad med följande inställningar:

    - **Tabell:** *Tillfälliga arbetstransaktioner*
    - **Härlett register:** *Tillfälliga arbetstransaktioner*
    - **Fält:** *Ordernummer*
    - **Sökriktning:** *Stigande*

    > [!IMPORTANT]
    > Om du vill undvika att behandla alla andra öppna behållare och påskynda processen genom att kontrollera en behållare i taget kan du bara använda *förpacka i aktuell behållare* förutom att sortera efter ordernummer. Den här kombinationen fungerar som en arbetsbrytning i en arbetsmall.

1. Stäng dialogrutan för frågeredigeraren genom att välja **OK**.
1. Medan raden för den nya mallen fortfarande är markerad väljer du **Blandade begränsningar för behållare** i åtgärdsfönstret.

    Du lägger nu till en begränsning som placerar artiklar från en enskild order i en enda behållare. Artiklar från alla andra order kommer att förvaras i en separat behållare.

1. Välj **Ny** om du vill skapa en blandad begränsning med följande inställningar:

    - **Register:** *Försäljningsorder*
    - **Fält markeras:** *SalesId* (Fältet visas som *Försäljningsorder* i rutnätet.)

1. Välj **OK** för att lägga till begränsning.
1. Stäng sidan.

### <a name="set-up-a-wave-template-for-containerization"></a>Ställa in en påfyllnadsmall för skapande av behållare

Så här ställer du in en påfyllnadsmall.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. I listruta ange fältet **Malltyp för påfyllnad** till *Leverans*.
1. Välj mallen **63 skapa behållare** i listan.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Metoder** i kolumnen **Valda metoder** hittar du följande rad:

    - **Metodnamn:** *skapande av behållare*
    - **Namn:** *skapande av behållare*

1. Ställ in fältet **Kod för påfyllnadssteg** för den här raden till *234*.

### <a name="set-up-a-work-template"></a>Ställ in en arbetsmall

Så här ställer du in en arbetsmall.

1. Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetsmallar**.
1. Ställ in fältet **Arbetsordertyp** till *Försäljningsorder*.
1. I rutnätet **Översikt** välj arbetsmallen som ska användas för packning av enstaka beställningar per behållare. För detta scenario, välj mallen **63 välj till behållare**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. En dialogruta för standard frågeredigeraren visas. Ange något av följande rader på fliken **Sortering**:

    - Rad 1:

        - **Tabell:** *Tillfälliga arbetstransaktioner*
        - **Härlett register:** *Tillfälliga arbetstransaktioner*
        - **Fält:** *leverans-ID*
        - **Sökriktning:** *Stigande*

    - Rad 2:

        - **Tabell:** *Tillfälliga arbetstransaktioner*
        - **Härlett register:** *Tillfälliga arbetstransaktioner*
        - **Fält:** *Ordernummer*
        - **Sökriktning:** *Stigande*

    - Rad 3:

        - **Tabell:** *Tillfälliga arbetstransaktioner*
        - **Härlett register:** *Tillfälliga arbetstransaktioner*
        - **Fält:** *Behållar-ID*
        - **Sökriktning:** *Stigande*

1. Stäng dialogrutan för frågeredigeraren genom att välja **OK**.
1. Följande meddelande kan visas: "gruppering återställs, fortsätt?" Klicka på **Ja** när du vill fortsätta.
1. När mallen **63 välj till behållare** fortfarande är markerad, välj **Arbetsuppgiftshuvudet delas** i åtgärdsfönstret.

    Du använder nu inställningar för att bryta arbetet så att varje behållare i ordern kopplas till en arbetsorder.

1. Markera kryssrutan **Gruppera efter det här fältet** för varje rad på sidan **Avbrott i arbetshuvud** (**Leverans-ID**, **Ordernummer** och **Behållar-ID**).
1. Stäng sidan.

### <a name="set-up-shipment-consolidation-policies"></a>Ange policyer för leveranskonsolidering

Så här ställer du in en konsolideringspolicy för leveranser.

1. Gå till **Warehouse managements \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.
1. I listfönstret, ange **Policytyp** i fältet till *Försäljningsorder*.
1. Välj **Standard** policy i listan.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Konsolideringsfält**, i listan **Valda fält**, markerar du den rad där fältet **Fältnamn** är inställt på *Ordernummer*.
1. Välj knappen **Ta bort** ![Vänster pil.](media/backward-button.png) om du vill flytta fältet till listan **Återstående fält**.
1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-physical-dimensions-for-the-product"></a>Ställ in fysiska produktdimensioner för produkten

Ställ in fysiska dimensioner för de produkter som ska användas i det här scenariot genom att följa dessa steg.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj produkten där fältet **Artikelnummer** är inställt på *A0001*.
1. I åtgärdsfönstret, på fliken **Hantera lager**, i gruppen **Lagerställe**, väljer du **Fysiska dimensioner**.
1. På sidan **Fysiska dimensioner** bör du se följande rad i rutnätet:

    - **Enhet:** *st*
    - **Bruttovikt:** *3,00*
    - **Bredd:** *2,00*
    - **Djup:** *2,00*
    - **Höjd:** *4,00*
    - **Volym:** *16,00*

1. Stäng sidan.
1. Välj produkten där fältet **Artikelnummer** är inställt på *A0002*.
1. I åtgärdsfönstret, på fliken **Hantera lager**, i gruppen **Lagerställe**, väljer du **Fysiska dimensioner**.
1. På sidan **Fysiska dimensioner** bör du se följande rad i rutnätet:

    - **Enhet:** *st*
    - **Bruttovikt:** *4,00*
    - **Bredd:** *3,00*
    - **Djup:** *1,00*
    - **Höjd:** *3,00*
    - **Volym:** *9,00*

### <a name="create-sales-order-1"></a>Skapa försäljningsorder 1

Följ dessa steg för att skapa en försäljningsorder.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. En dialogruta visas där du kan skapa en ny försäljningsorder. Ange följande värden.

    - **Kundkonto:** *US-001*
    - **Lagerställe:** *63*

1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. På snabbfliken **Försäljningsorderrader**, lägg till följande försäljningsrader:

    - Rad 1:

        - **Artikelnummer:** *A0001*
        - **Kvantitet:** *2*

    - Rad 2:

        - **Artikelnummer:** *A0002*
        - **Kvantitet:** *2*

1. Markera den första raden och välj sedan **Lager \> Reservation**.
1. På sidan **Reservation** väljer du **Reservera parti**. Stäng sidan.
1. Upprepa de två föregående stegen för den andra raden.
1. Stäng sidan.

### <a name="create-sales-order-2"></a>Skapa försäljningsorder 2

Följ dessa steg för att skapa en andra försäljningsorder.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. En dialogruta visas där du kan skapa en ny försäljningsorder. Ange följande värden.

    - **Kundkonto:** *US-001*
    - **Lagerställe:** *63*

1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. På snabbfliken **Försäljningsorderrader**, lägg till följande försäljningsrader:

    - Rad 1:

        - **Artikelnummer:** *A0001*
        - **Kvantitet:** *4*

    - Rad 2:

        - **Artikelnummer:** *A0002*
        - **Kvantitet:** *4*

1. Markera den första raden och välj sedan **Lager \> Reservation**.
1. På sidan **Reservation** väljer du **Reservera parti**. Stäng sidan.
1. Upprepa de två föregående stegen för den andra raden.
1. Stäng sidan.

### <a name="create-the-load"></a>Skapa last

Skapa en beläggning för varje orderuppsättning som du har skapat för scenariot och sedan släppa den till lagerstället.

1. Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.
1. På fliken **Försäljningsrader** letar du upp och markerar alla försäljningsorderrader från försäljningsordern som du skapat för det här scenariot.
1. I Åtgärdsfönster, på fliken **Tillgång och efterfrågan** i gruppen **Lägg till** välj **Till ny last**. De markerade orderraderna läggs till i en ny beläggning.
1. I dialogrutan **Malltilldelning för beläggning**, i fältet **ID för beläggningsmall**, väljer du en beläggningsmall som exempelvis *40' behållare*.
1. Välj **OK** för att stänga dialogrutan.
1. I avsnittet **Beläggningar** söker du upp samt väljer den beläggning du just skapat.
1. Välj **Frisläpp \> frisläpp till lagerställe**.
1. I dialogrutan **Släpp till lagerställe** välj **OK** om du vill frisläppa den valda beläggningen till lagerstället.

### <a name="verify-the-shipments-and-containers"></a>Kontrollera försändelser och behållare

I följande procedur kan du kontrollera försändelser som har skapats. Använd den när du vill granska den order du skapat för det här scenariot för att se till att du får de förväntade resultaten.

1. Gå till **Warehouse management \> Leveranser \> Alla leveranser**.
1. Sök efter och välj den försändelse som skapades för inläsningen som du just frisläppde.
1. Öppna fliken arbetsflöde i åtgärdsfönstret **Transport** och välj **Visa behållare**.
1. Bekräfta att artiklarna från försäljningsorderna var behållare i två olika behållare.

## <a name="additional-resources"></a>Ytterligare resurser

- [Skapande av behållare](wave-containerization.md)
