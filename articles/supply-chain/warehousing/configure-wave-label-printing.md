---
title: Utskrift av påfyllnadsetikett
description: Det här ämnet beskriver utskrift av påfyllnadsetikett och förklarar hur du ställer in det.
author: perlynne
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 6b75dcb7d56648f3be291cb1c09ec57a53477ec0
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344184"
---
# <a name="wave-label-printing"></a>Utskrift av påfyllnadsetikett

[!include [banner](../includes/banner.md)]

Utskrift av påfyllnadsetikett ger en alternativ metod för att skriva ut etiketter genom att introducera en ny påfyllnadsmetod som gör att du kan skapa och skriva ut etiketter direkt från påfyllnadsmallen under påfyllnadskörningen. Därför är etiketterna redan tillgängliga innan medarbetare kör arbetsordern på en mobil enhet. Arbetare kan sedan koppla de begärda etiketterna under plockning i stället för efter plockning.

Utskrift av påfyllnadsetikett använder zebraprogrammeringspråket (ZPL) när du skapar etikettlayout. En etikettlayout är uppdelad i tre avsnitt (rubrik, brödtext och sidfot) som tillåter etiketter som har en upprepande struktur. Mallar för etikettutskrift anger du vilket system som etikettexten ska använda. Användare kan ange vilken skrivare som ska användas. De kan också skriva ut etiketter på flera skrivare samtidigt, eftersom de kräver det. Sidan **påfyllnadsetiketthistoriken** visar en post över alla etiketter som har skapats med hjälp av den här inställningen.

Du kan skriva ut och sortera etiketter baserat på arbetsrubriker, du kan skriva ut avbrottsetiketter per arbetsrubrik och du kan skriva ut behållarens innehållsetiketter, ärendeetiketter och andra liknande etiketter.

> [!NOTE]
> Den här funktionen ersätter inte de befintliga funktionerna för etikettutskrift som baseras på dokumentflödet.

Utskrift av påfyllnadsetikett ger följande förbättringar:

- Skriv ut etiketter enligt antalet kartonger på en enda arbetsrad, utan att använda skapande av behållare. (En "kartong" är en enhet som har angetts för enhetssekvensgruppraderna.)
- Skriv ut flera olika etikettserier (t.ex. kartonger och lastpallsetiketter).
- Inkludera etikettuppräkning (t.ex. 1/124, 2/124... 124/124) och definiera intervallet för uppräkningen (t.ex. arbetsrad, lastrad eller leverans).
- Skapa och skriv ut ett fraktsedels-ID på etiketter innan fraktsedeln genereras.
- Skapa en unik serie för seriell leveransbehållare (SSCC) för varje kartong och inkludera den på varje etikett.
- Skapa GS1-kompatibla nummerserier för fraktsedels-ID och SSCC.
- Skriv ut etiketterna på både mobila enheter och den avancerade klienten.
- Annullera etiketter (t.ex. i korta plockningsscenarier) och skriv ut dem igen.
- Rensa historik för påfyllnadsetikett.
- Förbättringar av layouter av dokumentflöde delas mellan dokumentflödets layout och påfyllnadsetikettens layout. (Mer information finns i [Layout för dokumentflöde för ID-nummer](../warehousing/document-routing-layout-for-license-plates.md) .)

Dessa förbättringar gör det effektivare att märka kartonger före palletering. De gynnar främst företag som levererar till stora återförsäljare som automatiskt bekräftar orderkvitton genom att söka igenom varje kartong separat.

> [!NOTE]
> Du kan implementera konfigurationsscenarier som beskrivs i det här avsnittet, antingen separat eller i kombination, beroende på dina affärsbehov. Du kan skapa flera påfyllnadsetikettmallar som fungerar i ordningsföljd (som illustreras i scenario 3). Du kan till exempel använda scenario 1 för att skriva ut kartonger och scenario 2 om du vill skriva ut lastpallsetiketter (om lastpallar i lagret varierar i storlek och sammansättning).

## <a name="turn-on-the-wave-label-printing-feature"></a>Aktivera funktionen utskrift av påfyllnadsetiketter

Innan du kan använda funktionen *utskrift av påfyllnadsmall* den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Warehouse management*
- **Funktionsnamn:** *utskrift av påfyllnadsetiketter*

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a>Scenario 1: utskrift av påfyllnadsetiketter där en enskild påfyllnadsetikett genereras

Det här scenariot visar hur ett företag kan skriva ut leveransetiketter för en stor återförsäljare som automatiskt bekräftar orderkvitton genom att söka igenom varje kartong separat.

Det här scenariot visar komplett flöde.

### <a name="make-demo-data-available"></a>Gör demodata tillgängliga

För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Kontrollera att påfyllnadsetikett metoden är tillgänglig

Du måste kanske återskapa dina metoder för påfyllnadsprocess för att göra påfyllnadsetikett metoden tillgänglig.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.
1. Kontrollera att **waveLabelPrinting** finns i listan. Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.

### <a name="configure-a-wave-template"></a>Konfigurera en påfyllnadsmall

Med påfyllnadsmallar kan du länka specifika förekomster av påfyllnadsmetoder till en motsvarande påfyllnadsetikettsmall.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. Välj en mall som **62 standard för leverans**.
1. På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.
1. I kolumnen **Valda metoder** välj metoden **Utskrift av påfyllnadsetiketter** och ange dess fält **Kod för påfyllnadssteg** till *PrintLabel*. För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Skapa en layout för påfyllnadsetiketten

Etikettlayouten bestämmer vilken information som ska skrivas ut på etiketten och hur den visas. Här anger du koden för ZPL som skickas till skrivaren.

1. Gå till **Warehouse management \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.
1. Skapa en post med följande inställningar:

    - **Etikettlayout-ID:** *kartong*
    - **Beskrivning:** *kartong (SSCC)*

1. Klicka på **Spara** i åtgärdsfönstret.
1. I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.

    Sidan **Inställningar för påfyllnadsetikettrad** visas. Här kan du konfigurera den dynamiska delen av etiketten.

1. Lägg till en rad med följande inställningar:

    - **Rad-ID:** *WaveLabel*
    - **Radtabellnamn:** *WHSWaveLabel*
    - **Radens startposition:** *0*

        I det här fältet definieras den lodräta position där raden ska börja etiketten.

    - **Radhöjd:** *0*

        I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard. Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter. Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).

    - **Rader per sida:** *1*

        I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.

        > [!NOTE]
        > Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.

1. Stäng sidan.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *arbetstyp*
    - **Kriterier:** *Plocka*

    Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.

1. Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.
1. Stäng dialogrutan frågeredigeraren.
1. På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**. I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik. Om du till exempel använder Zebra-skrivare kan du använda följande kod.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text. Här är ett exempel:

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot. Här är ett exempel:

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Installationen kommer att skriva ut en kopia av varje etikett. Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs. Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.

Nu kan du använda din etikett.

### <a name="create-a-wave-label-type"></a>Skapa en typ för påfyllnadsetiketten

Påfyllnadsetikettyper används för att länka påfyllnadsetikettmallar till en enhet på enhetssekvensgrupprader.

1. Gå till **Warehouse management \> Inställningar \> Dokumentflöde \> Typer av påfyllnadsetikett**.
1. Lägg till en typ av påfyllnadsetikett med följande inställningar:

    - **Etikettyp:** *kartong*
    - **Beskrivning:** *kartong*

### <a name="set-up-unit-sequence-groups"></a>Konfigurera enhetssekvensgrupper

Ställ sedan in enhetsseriegruppen för typ av påfyllnadsnivå.

1. Gå till **Warehouse management \> Inställningar \> Lagerställe \> Enhetsseriegrupp**.
1. Välj gruppen **Ea Box PL**.
1. För raden **ruta** ange fältet **typ av påfyllnadsnivå** till *kartong*.

### <a name="create-a-wave-label-template"></a>Skapa en mall för påfyllnadsetikett

Skapa sedan mall för påfyllnadsetikett för typen av påfyllnadsetikett.

1. Gå till **Warehouse management \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.
1. Lägg till en mall för påfyllnadsnivå och ange följande värden i rubriken:

    - **Namn på etikettmallen:** *kartongetiketter*
    - **Beskrivning:** *kartongetiketter*
    - **Kod för påfyllnadssteg:** *PrintLabel*
    - **Lagerställe:** *62*

1. På snabbfliken **Allmänt** ställer du in fältet **typ av påfyllnadsetikett** till *kartong*.
1. På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en ny rad med följande inställningar:

    - **Etikettlayout-ID:** *kartong*
    - **Skrivarnamn:** Välj en lämplig ZPL-skrivare.
    - **Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)

1. Klicka på **Spara** i åtgärdsfönstret.
1. Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto. På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**. I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:

    - **Register:** *försändelser*
    - **Härlett register:** *försändelser*
    - **Fält:** *Kontonummer*
    - **Kriterier:** Ange relevant kundkontonummer.

    När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.

1. I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.
1. I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *referens till läs in rad-ID (post-ID)*
    - **Sökriktning:** *Stigande*

1. Stäng dialogrutan för frågeredigeraren genom att välja **OK**.
1. En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning. Klicka på **Ja** när du vill fortsätta.
1. I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.
1. I dialogrutan **mallgruppen för påfyllnadsetikett** välj raden där fältet **referensfältnamn** anges till *referens till läs in rad-ID* och markerar sedan kryssrutan **etikettversions-ID** för den här raden.

    > [!NOTE]
    > Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen. Denna etikettserie kan skrivas ut på etikettlayouten.

### <a name="configure-number-sequence-extensions"></a>Konfigurera nummerserietillägg

Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier. Den här konfigurationen är valfri för det aktuella scenariot. Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Skapa en försäljningsorder och släpp den på lagerstället

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Lagerställe:** *62*

1. Lägg till två försäljningsorderrader med följande inställning:

    - Försäljningsorderrad 1:

        - **Artikelnummer:** *A0001*
        - **Kvantitet:** *9024*
        - **Enhet:** *ea* (9024 ea = 376 låda = 47 PL)

    - Försäljningsorderrad 2:

        - **Artikelnummer:** *A0002*
        - **Kvantitet:** *9016*
        - **Enhet:** *ea* (9016 ea = 322 box = 46 PL)

    > [!NOTE]
    > Artiklarna och kvantiteterna som anges här är endast exempel. De måste använda den enhetsseriegrupp som du definierade tidigare, och lämpliga enhetskonverteringar från *ea* till *Box* till *PL* måste definieras för dem och de måste ha lager i lagerställe *62*. Mer information finns i [måttenhet och lagerprinciper](unit-measure-stocking-policies.md).

1. Välj försäljningsorderrad 1. I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.
1. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.
1. Upprepa steg 4 och 5 för försäljningsorderrad 2.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    Då inträffar följande händelser:

    - I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett. Etikettlayouten används för att definiera etikettens format, och resultatet blir en etikett som skrivs ut på den skrivare som väljs i etikettmallen.
    - Påfyllnadsetiketter genereras och skrivs ut. Antalet etiketter är lika med antalet kartonger (i det här exemplet är 376 boxetiketter för rad 1 och 322 boxetiketter för rad 2).
    - Ett nytt fraktsedels-ID genereras för leveranserna. Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**. 

Du kan visa och skriva ut påfyllnadsetiketter på följande sidor. I åtgärdsfönstret, på varje sida, på fliken **Leveranser**, i gruppen **Relaterad information**, väljer du **påfyllnadsetiketter**.

- Alla leveranser \> leveransinformation
- Alla laster \> Läs in information
- Alla påfyllnader
- Påfyllnadsetiketter
- Etiketthistorik för påfyllnad

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a>Scenario 2: påfyllnadsetikett utskrift för skapande av behållare (utan påfyllnadsetikettposter)

I det här scenariot kan du skriva ut påfyllnadsetiketter när du använder skapande av behållare för att automatiskt dela upp objekt i kartonger och därför inte kräva en påfyllnadsetikettpost. I det här fallet fungerar behållar-ID som platshållare för SSCC.

Här är de viktigaste skillnaderna mellan det här scenariot och scenario 1:

- **Mallar för påfyllnadsetiketter:** du väljer ingen typ av påfyllnadsetikett i mallen för påfyllnadsetiketter och du behöver inte använda en gruppering för att skapa etiketter. Annars kan du konfigurera mallen för påfyllnadsetikett och länka till påfyllnadsmallen på samma sätt som beskrivs i scenario 1. Du måste lämna typ av påfyllnadsetikett tom om du vill förhindra att påfyllnadsetiketter genereras.
- **Layout för påfyllnadsetiketter:** du kan konfigurera radinställningarna för layouten för påfyllnadsetiketter för arbetsrader i stället för påfyllnadsetikettposter. Du måste konfigurera radinställningen för etikettlayout med hjälp av registret **WHSWorkLine** i stället för registret **WHSWaveLabel**. Inställningen **rader per sida** styr antalet rader som brödtextavsnittet ska ha. 

Den här konfigurationen är också lämplig för affärsscenarier där flera olika artiklar förpackas i en etikettruta eller till en lastpall, och denna förpackningsprocess kan definieras genom att arbetet skapas (t.ex. arbete som grupperats per leverans).

Det här scenariot visar komplett flöde.

### <a name="make-demo-data-available"></a>Gör demodata tillgängliga

För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Kontrollera att påfyllnadsetikett metoden är tillgänglig

Du måste kanske återskapa dina metoder för påfyllnadsprocess för att göra påfyllnadsetikett metoden tillgänglig.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.
1. Kontrollera att **waveLabelPrinting** finns i listan. Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.

### <a name="set-up-a-wave-template"></a>Ställa in en påfyllnadsmall

Med påfyllnadsmallar kan du länka specifika förekomster av påfyllnadsmetoder till en motsvarande påfyllnadsetikettsmall.

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. Välj en mall som **63 skapande av behållare**.
1. På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.
1. I kolumnen **Valda metoder** välj metoden **Utskrift av påfyllnadsetiketter** och ange dess fält **Kod för påfyllnadssteg** till *PrintLabel*. För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Skapa en layout för påfyllnadsetiketten

1. Gå till **Warehouse management \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.
1. Skapa en post med följande inställningar:

    - **Etikettlayout-ID:** *kartong*
    - **Beskrivning:** *kartong (SSCC)*

1. Klicka på **Spara** i åtgärdsfönstret.
1. I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.

    Sidan **Inställningar för påfyllnadsetikettrad** visas. Här kan du konfigurera den dynamiska delen av etiketten.

1. Lägg till en rad med följande inställningar:

    - **Rad-ID:** *WorkLine*
    - **Radtabellnamn:** *WHSWorkLine*
    - **Radens startposition:** *500*

        I det här fältet definieras den lodräta position där raden ska börja etiketten.

    - **Radhöjd:** *-50*

        I det här fältet definieras höjden på varje rad. Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter.

    - **Rader per sida:** *5*

        I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.

        > [!NOTE]
        > Denna inställning kommer att skriva ut flera ZPL-etiketter per arbete, där varje sida kan innehålla upp till fem arbetsrader. Om en etikett till exempel skrivs ut för en behållare med 12 rader skrivs tre etiketter ut. Om du vill skriva ut en separat etikett för varje plockningsrad anger du det här värdet till *1*.

1. Stäng sidan.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *arbetstyp*
    - **Kriterier:** *Plocka*

1. Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.
1. Stäng dialogrutan frågeredigeraren.
1. På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**. I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik. Om du till exempel använder Zebra-skrivare kan du använda följande kod.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text. Här är ett exempel:

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot. Här är ett exempel:

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Installationen kommer att skriva ut en kopia av varje etikett. Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs. Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.

Nu kan du använda din etikett.

### <a name="create-a-wave-label-template"></a>Skapa en mall för påfyllnadsetikett

1. Gå till **Warehouse management \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.
1. Lägg till en mall för påfyllnadsnivå och ange följande värden i rubriken:

    - **Namn på etikettmallen:** *behållaretiketter*
    - **Beskrivning:** *behållaretiketter*
    - **Kod för påfyllnadssteg:** *PrintLabel*
    - **Lagerställe:** *63*

1. På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:

    - **Etikettlayout-ID:** *behållare*
    - **Skrivarnamn:** Välj en lämplig ZPL-skrivare.
    - **Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)

1. Klicka på **Spara** i åtgärdsfönstret.
1. Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto. På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**. I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:

    - **Register:** *försändelser*
    - **Härlett register:** *försändelser*
    - **Fält:** *Kontonummer*
    - **Kriterier:** Ange relevant kundkontonummer.

    När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.

### <a name="configure-number-sequence-extensions"></a>Konfigurera nummerserietillägg

Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier. Den här konfigurationen är valfri för det aktuella scenariot. Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Skapa en försäljningsorder och släpp den på lagerstället

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Lagerställe:** *63*

1. Lägg till fem försäljningsorderrader:

    - Försäljningsorderrad 1:

        - **Artikelnummer:** *A0001*
        - **Kvantitet:** *10*

    - Försäljningsorderrad 2:

        - **Artikelnummer:** *A0002*
        - **Kvantitet:** *20*

    - Försäljningsorderrad 3:

        - **Artikelnummer:** *L0006*
        - **Kvantitet:** *20*

    - Försäljningsorderrad 4:

        - **Artikelnummer:** *L0100*
        - **Kvantitet:** *40*

    - Försäljningsorderrad 5:

        - **Artikelnummer:** *L0101*
        - **Kvantitet:** *50*

    > [!NOTE]
    > Artiklarna och kvantiteterna som anges här är endast exempel. De måste ha lager i det angivna lagerstället.

1. Välj försäljningsorderrad 1. I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.
1. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.
1. Upprepa steg 4 och 5 för varje ytterligare försäljningsorderrad.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    Då inträffar följande händelser:

    - I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett. Etikettlayouten används för att definiera etikettens format, och slutresultatet blir en etikett som har fem rader och som skrivs ut på den skrivare som väljs i etikettmallen.
    - Ett nytt fraktsedels-ID genereras för leveranserna. Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**. 

Du kan skriva ut dessa påfyllnadsetiketter igen genom att gå till **Warehouse management \> Frågor och rapporter \> Påfyllnadsetiketthistorik**.

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a>Scenario 3: utskrift av påfyllnadsetikett för etiketter med flera nivåer

Det här scenariot visar hur du använder funktionen utskrift av påfyllnadsetikett när lagerprocesserna kräver flera nivåer för leveransetiketter. Till exempel kan separata etiketter behöva skrivas ut för kartonger och lastpallar, och en avbrottsetikett måste skrivas ut för en hel leverans. Avbrottsetiketter är en separat typ av etikett som kan användas som avgränsare mellan rullar och behållare, t. ex. etiketter för leverans-ID och en streckkod, så att etiketterna enkelt kan sorteras när de har skrivits ut.

Den huvudsakliga skillnaden mellan konfigurationen av scenariot och konfigurationen av scenario 1, förutom att bryta etiketter är aktiverade, är att flera typer av påfyllnadetiketter måste associeras med påfyllnadsetikettmallen och enhetssekvensgruppraderna. För att kunna utföra den här konfigurationen ställer du in följande element för det här scenariot:

- **Metoder för påfyllnadsbearbetning:** du markerar en påfyllnadsetiketts metod som "upprepningsbar", lägger till den två (eller fler) tiderna i påfyllnadsmallen och ställer in olika koder för påfyllnadssteg.
- **Mallar för påfyllnadsetikett:** du kommer att konfigurera mallarna för påfyllnadsetikett och länka dem till påfyllnadsmallen. Varje påfyllnadsetikettmall har en egen typ av påfyllnadsetikett.
- **Layout för påfyllnadsetiketter:** du kan skapa flera layouter för påfyllnadsetiketter. Det finns en separat etikettlayout för varje "nivå" med etiketter och det får också en layout för avbrottsetiketten.

Det här scenariot visar komplett flöde.

### <a name="make-demo-data-available"></a>Gör demodata tillgängliga

För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.

### <a name="set-up-a-wave-process-method"></a>Ställa in en påfyllnadsprocessmetod

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.
1. Kontrollera att **waveLabelPrinting** finns i listan. Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.
1. För metoden **waveLabelPrinting** markera kryssrutan **gör metoden upprepningsbar**.

### <a name="set-up-a-wave-template"></a>Ställa in en påfyllnadsmall

1. Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
2. Välj en mall som **62 standard för leverans**.
3. På snabbfliken **metoder** flyttar du metoden **utskrift av påfyllnadsetiketter** till kolumnen **valda metoder**.
4. I kolumnen **valda metoder** tilldelar du ett värde för **Kod för påfyllnadssteg** som *kartong* till metoden **utskrift av påfyllnadsetikett**. För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).
5. Flytta metoden **utskrift av påfyllnadsetikett** till kolumnen **valda metoder** en andra gång.
6. I kolumnen **valda metoder** tilldelar du ett annat värde för **Kod för påfyllnadssteg** som *lastpall* till den andra metoden **utskrift av påfyllnadsetikett**. För mer information om koder för påfyllnadssteg, se [Koder för påfyllnadssteg](wave-step-codes.md).

### <a name="create-three-wave-label-layouts"></a>Skapa tre layouter för påfyllnadsetiketten

1. Gå till **Warehouse management \> Inställningar \> Dokumentflöde \> Layout för påfyllnadsetikett**.
1. Skapa en post med följande inställningar:

    - **Etikettlayout-ID:** *kartong*
    - **Beskrivning:** *kartong (SSCC)*

1. Klicka på **Spara** i åtgärdsfönstret.
1. I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.

    Sidan **Inställningar för påfyllnadsetikettrad** visas. Här kan du konfigurera den dynamiska delen av etiketten.

1. Lägg till en rad med följande inställningar:

    - **Rad-ID:** *WaveLabel*
    - **Radtabellnamn:** *WHSWaveLabel*
    - **Radens startposition:** *0*

        I det här fältet definieras den lodräta position där raden ska börja etiketten.

    - **Radhöjd:** *0*

        I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard. Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter. Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).

    - **Rader per sida:** *1*

        I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.

        > [!NOTE]
        > Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.

1. Stäng sidan.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *arbetstyp*
    - **Kriterier:** *Plocka*

    Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.

1. Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den. 
1. Stäng dialogrutan frågeredigeraren.
1. På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**. I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik. Om du till exempel använder Zebra-skrivare kan du använda följande kod.


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text. Här är ett exempel:

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot. Här är ett exempel:

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Installationen kommer att skriva ut en kopia av varje etikett. Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs. Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.

1. Nu kan du använda din första etikett.
1. Skapa en andra layoutpost med följande inställningar:

    - **Etikettlayout-ID:** *lastpall*
    - **Beskrivning:** *lastpall*

1. Klicka på **Spara** i åtgärdsfönstret.
1. I åtgärdsfönstret, välj **Inställningar för påfyllnadsetikettrad**.

    Sidan **Inställningar för påfyllnadsetikettrad** visas. Här kan du konfigurera den dynamiska delen av etiketten.

1. Lägg till en rad med följande inställningar:

    - **Rad-ID:** *WaveLabel*
    - **Radtabellnamn:** *WHSWaveLabel*
    - **Radens startposition:** *0*

        I det här fältet definieras den lodräta position där raden ska börja etiketten.

    - **Radhöjd:** *0*

        I det här fältet definieras höjden på varje rad (i punkter) enligt ZPL-standard. Radhöjden är positiv för vågräta etiketter och är negativ för lodräta etiketter. Eftersom det bara finns en rad i det här exemplet kan du ställa in värdet på *0* (noll).

    - **Rader per sida:** *1*

        I det här fältet definieras antalet rader som kan skrivas ut på varje etikett.

        > [!NOTE]
        > Den här inställningen gör att en separat ZPL-etikett skrivs ut för varje post i tabellen med påfyllnadsetiketter.

1. Stäng sidan.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *arbetstyp*
    - **Kriterier:** *Plocka*

    Den här frågan ser till att endast arbetsrader av typen plockning skrivs ut på etiketten, inte artikelrader av typen radtyp.

1. Om du vill kunna skriva ut fraktsedels-ID väljer du på fliken **kopplingar**, sedan **arbetsrader** och kopplar tabellen **leveranser** till den.
1. Stäng dialogrutan frågeredigeraren.
1. På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**. I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du koden för önskad rubrik. Om du till exempel använder Zebra-skrivare kan du använda följande kod.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. I avsnittet **brödtext** i fältet **etikettext** anger du ZPL-koden för önskad text. Här är ett exempel:

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. I avsnittet **brödtext** i fältet **etikettsidfot** anger du ZPL-koden för önskad sidfot. Här är ett exempel:

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Installationen kommer att skriva ut en kopia av varje etikett. Om du vill ha fler kopior (t.ex. en kopia för varje sida av lastpallen) anger du värdet **n** för avsnittet **\^PQn** i sidfoten till det antal kopior som krävs. Om du till exempel vill skriva ut fyra kopior av varje etikett anger du **\^PQ4**.

1. Nu kan du använda din andra etikett.
1. Skapa en tredje layoutpost med följande inställningar:

    - **Etikettlayout-ID:** *Avbrott*
    - **Beskrivning:** *avbrottsetikett*

1. Klicka på **Spara** i åtgärdsfönstret.
1. På snabbfliken **Layout för skrivartext** finns tre avsnitt där du kan skriva skrivarkod: **rubrikavsnitt**, **brödtext** och **sidfotsavsnitt**. I avsnittet **rubrikavsnitt** i fältet **etikettrubrik** anger du ZPL-koden för önskad rubrik. Här är ett exempel:

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. Den här gången behövs ingen brödtext. Ange därför bara den text som krävs i avsnittet **sidfotsavsnitt**. Här är ett exempel:

    ```plaintext
    ^XZ
    ```

    Nu kan du använda din tredje etikett.

    > [!NOTE]
    > Den tredje etiketten är en avbrottsetikett som ska användas som avgränsare mellan etikettrullar.

### <a name="create-two-wave-label-types"></a>Skapa två typer av påfyllnadsetiketten

1. Gå till **Warehouse management \> Inställningar \> Dokumentflöde \> Typer av påfyllnadsetikett**.
1. Skapa en post med följande inställningar:

    - **Etikettyp:** *kartong*
    - **Beskrivning:** *kartong*

1. Skapa en andra post med följande inställningar:

    - **Etikettyp:** *lastpall*
    - **Beskrivning:** *lastpall*

### <a name="set-up-unit-sequence-groups"></a>Konfigurera enhetssekvensgrupper

1. Gå till **Warehouse management \> Inställningar \> Lagerställe \> Enhetsseriegrupp**.
1. Välj eller skapa en grupp för **Ea Box PL**.
1. För raden **ruta** ange fältet **typ av påfyllnadsnivå** till *kartong*.
1. För raden **PL** ange fältet **typ av påfyllnadsnivå** till *lastpall*.

### <a name="create-wave-label-templates"></a>Skapa mallar för påfyllnadsetikett

1. Gå till **Warehouse management \> Inställningar \> Dokumentflöde \> Mall för påfyllnadsetikett**.
1. Skapa en etikettmall med följande inställningar:

    - **Namn på etikettmallen:** *kartongetiketter*
    - **Beskrivning:** *kartongetiketter*
    - **Kod för påfyllnadssteg:** *kartong*
    - **Lagerställe:** *62*

1. På snabbfliken **allmänna** i fältet **typ av påfyllnadsetikett** väljer du ett värde som *kartong*.
1. På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:

    - **Etikettlayout-ID:** *kartong*
    - **Skrivarnamn:** Välj en lämplig ZPL-skrivare.
    - **Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)

1. Klicka på **Spara** i åtgärdsfönstret.
1. Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto. På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**. I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:

    - **Register:** *försändelser*
    - **Härlett register:** *försändelser*
    - **Fält:** *Kontonummer*
    - **Kriterier:** Ange relevant kundkontonummer.

    När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren.

1. I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.
1. I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *referens till läs in rad-ID (post-ID)*
    - **Sökriktning:** *Stigande*

1. Lägg till en andra rad med följande inställningar:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *leverans-ID*
    - **Sökriktning:** *Stigande*

1. Stäng dialogrutan för frågeredigeraren genom att välja **OK**.
1. En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning. Klicka på **Ja** när du vill fortsätta.
1. I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.
1. I dialogrutan **mallgruppen för påfyllnadsetikett** för raden där fältet **Namn på referensfält** anges till *leverans-ID* anger du följande värden:

    - **Skriv ut avbrottsetikett:** Markera den här kryssrutan.
    - **Layout-ID för etikett:** Välj en avbrottsetikett. (Välj t.ex. etikettlayouten *Avbrott* som du skapade tidigare i det här scenariot.)
    - **Skrivarnamn:** Välj skrivare för avbrottsetiketten. (I syfte att dela upp etikettrullar bör du välja samma skrivare som väljs på snabbfliken **information om påfyllnadsetikettens mall**. Andra scenarier är dock möjliga.)

1. Från raden där fältet **Namn på referensfält** anges till *referens till läs in rad-ID*, markera kryssrutan **etikettversions-ID**.

    > [!NOTE]
    > Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen. Denna etikettserie kan skrivas ut på etikettlayouten. Dessutom kommer etiketter för olika försändelser att åtskiljas med den valda avbrottsetiketten.

1. Klicka på **OK** om du vill stänga dialogrutan **mallgruppen för påfyllnadsetikett**.
1. Skapa en andra etikettmall med följande inställningar:

    - **Namn på etikettmallen:** *lastpalletiketter*
    - **Beskrivning:** *lastpalletiketter*
    - **Kod för påfyllnadssteg:** *lastpall*
    - **Lagerställe:** *62*

1. På snabbfliken **allmänna** i fältet **typ av påfyllnadsetikett** väljer du ett värde som *lastpall*.
1. På snabbfliken **information om påfyllnadsetikettens mall** och lägg till en rad med följande inställningar:

    - **Etikettlayout-ID:** *lastpall*
    - **Skrivarnamn:** Välj en lämplig ZPL-skrivare.
    - **Kör fråga:** *Ja* (den här inställningen är valfri, men rekommenderas för optimal prestanda.)

1. Klicka på **Spara** i åtgärdsfönstret.
1. Valfritt: om du ställer in en kundspecifik etikettdesign måste du skapa en fråga för att hitta kundens konto. På snabbfliken **information om påfyllnadsetikettens mall** välj **Redigera fråga**. I frågeredigerarens dialogruta, på fliken **Intervall** lägg till en rad med följande värden:

    - **Register:** *försändelser*
    - **Härlett register:** *försändelser*
    - **Fält:** *Kontonummer*
    - **Kriterier:** Ange relevant kundkontonummer.

    När du är klar klickar du på **OK** för att stänga dialogrutan för frågeredigeraren. 

1. I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för frågeredigeraren för hela etikettmallen.
1. I frågeredigerarens dialogruta, på fliken **Sortera** lägg till en rad med följande värden:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *referens till läs in rad-ID (post-ID)*
    - **Sökriktning:** *Stigande*

1. Lägg till en andra rad med följande inställningar:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *leverans-ID*
    - **Sökriktning:** *Stigande*

1. Stäng dialogrutan för frågeredigeraren genom att välja **OK**.
1. En meddelande ruta ber dig bekräfta åtgärden grupperingsåterställning. Klicka på **Ja** när du vill fortsätta.
1. I åtgärdsfönstret, välj **mallgruppen för påfyllnadsetikett**.
1. I dialogrutan **mallgruppen för påfyllnadsetikett** för raden där fältet **Namn på referensfält** anges till *leverans-ID* anger du följande värden:

    - **Skriv ut avbrottsetikett:** Markera den här kryssrutan.
    - **Layout-ID för etikett:** Välj en avbrottsetikett. (Välj t.ex. etikettlayouten *Avbrott* som du skapade tidigare i det här scenariot.)
    - **Skrivarnamn:** Välj skrivare för avbrottsetiketten. (I syfte att dela upp etikettrullar bör du välja samma skrivare som väljs på snabbfliken **information om påfyllnadsetikettens mall**. Andra scenarier är dock möjliga.)

1. Från raden där fältet **Namn på referensfält** anges till *referens till läs in rad-ID*, markera kryssrutan **etikettversions-ID**.

    > [!NOTE]
    > Med den här inställningen skapas en etikettserie ("kartong 1 av X") per lastrad i hela påfyllnaden, oavsett inställningen för arbetsgrupperingen. Denna etikettserie kan skrivas ut på etikettlayouten. Dessutom kommer etiketter för olika försändelser att åtskiljas med den valda avbrottsetiketten.

### <a name="configure-number-sequence-extensions"></a>Konfigurera nummerserietillägg

Nummerserietillägg styr GS1 efterlevnaden av specifika nummerserier. Den här konfigurationen är valfri för det aktuella scenariot. Mer information och instruktioner för konfigurering finns i [Konfigurera tillägg för nummerserier](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Skapa en försäljningsorder och släpp den på lagerstället

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Lagerställe:** *62*

1. Lägg till två försäljningsorderrader:

    - Försäljningsorderrad 1:

        - **Artikelnummer:** *A0001*
        - **Kvantitet:** *9024*
        - **Enhet:** *ea* (9024 ea = 376 låda = 47 PL)

    - Försäljningsorderrad 2:

        - **Artikelnummer:** *A0002*
        - **Kvantitet:** *9016*
        - **Enhet:** *ea* (9016 ea = 322 box = 46 PL)

    > [!NOTE]
    > Artiklarna och kvantiteterna som anges här är endast exempel. De måste använda den enhetsseriegrupp som du definierade tidigare, och lämpliga enhetskonverteringar från *ea* till *Box* till *PL* måste definieras för dem och de måste ha lager i lagerställe *62*. Mer information finns i [måttenhet och lagerprinciper](unit-measure-stocking-policies.md).

1. Välj försäljningsorderrad 1. I avsnittet **Försäljningsorderrad** i menyn **Lager** välj **Reservationer**.
1. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** och stäng sedan sidan.
1. Upprepa steg 4 och 5 för försäljningsorderrad 2.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    Då inträffar följande händelser: 

    - I systemet bearbetas den skapade utleveransen med hjälp av mallen som inkluderar utskriftssteget för etikett. Etikettlayouten används för att definiera etikettens format, och resultatet blir en etikett som skrivs ut på den skrivare som väljs i etikettmallen.
    - Påfyllnadsetiketter genereras och skrivs ut. Antalet etiketter är lika med antalet kartonger (i det här exemplet är 376 boxetiketter för rad 1, 322 boxetiketter för rad 2, 47 PL-etiketter för rad 1, 47 PL-etiketter för rad 2 och två avbrottsetiketter med leverans-ID).
    - Ett nytt fraktsedels-ID genereras för leveranserna. Om du har konfigurerat nummerserietilläggen följer påfyllnadsetikett-ID nummerformatet **SSCC-18**. 

Du kan visa och skriva ut påfyllnadsetiketter på följande sidor:

- Alla leveranser \> leveransinformation
- Alla laster \> Läs in information
- Alla påfyllnader
- Påfyllnadsetiketter
- Etiketthistorik för påfyllnad

För de flesta av dessa sidor hittar du den relevanta funktionen genom att välja **Påfyllnadsetiketter** i gruppen **Relaterad information** i fliken **leveranser** i åtgärdsfönstret.

## <a name="additional-resources"></a>Ytterligare resurser

- [Skriva ut på nytt och annullera påfyllnadsetiketter](reprint-and-void-wave-labels.md)
- [Tidsplanera påfyllnadsetikett utskrift under påfyllnad](configure-task-based-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
