---
title: Ej fakturerad intäkt
description: Detta ämne beskriver hur du ställer in poster och konton för att använda funktionen ej fakturerad intäkt i prenumerationsfakturering.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: a70786291822a85ec41c98ab8ce706f2ad79b08d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691257"
---
# <a name="unbilled-revenue"></a>Ej fakturerad intäkt

Det här ämnet beskriver funktionen för ej fakturerad intäkt där du kan ta med beloppen för hela faktureringsscheman i balansräkningen. Dessa belopp inkluderas i ett konto för ej fakturerad intäkt och ett motkonto för ej fakturerad intäkt och kontraktet faktureras via avbetalningar.

## <a name="set-up-unbilled-revenue"></a>Ställ in ej fakturerad intäkt

Så här ställer du in ej fakturerad intäkt.

- På sidan **Återkommande faktureringsparametrar för kontrakt** ställ in fälten i avsnittet **Ej fakturerad intäkt**.
- Funktionen för ej fakturerade intäkter kan användas för artiklar där fältet **Artikeltyp** är inställt på **Standard**. Den kan också användas för de periodiseringsartiklar. Om du vill använda ej fakturerade intäkter med funktionen kortsiktigt ställer du in alternativen på sidan **Faktureringsparametrar för återkommande kontrakt**.

Så här ställer du in för att använda ej fakturerad intäkt.

1. På sidan **Inställningar för ej fakturerad intäkt** på fliken **Artiklar**, välj **Lägg till**.
2. Välj **artikelkod** på den nya raden, i artikelkoden.
3. I fältet **Artikelrelation** väljer du artikelrelationen.
4. Upprepa dessa steg för att lägga till fler rader.
5. Välj **Spara**.

Så här ställer du in för att använda ej fakturerad intäktskonto.

1. På sidan **Inställningar för ej fakturerad intäkt** på fliken **Konto**, välj **Lägg till**.
2. Välj **artikelkod** på den nya raden, i artikelkoden.
3. I fältet **Artikelrelation** väljer du artikelrelationen.
4. Välj konton för ej fakturerad intäkt, ej fakturerad rabatt och motkonto för ej fakturerad intäkt. Om du vill använda kortsiktiga konton måste du ställa in fältet **Kortfristig ej debiterar metod** till **Rullande perioder** eller **Fast år** på sid **Återkommande faktureringsparametrar för kontrakt**.
5. Upprepa dessa steg för att lägga till fler rader.
6. Välj **Spara**.

## <a name="use-unbilled-revenue"></a>Använd ej fakturerad intäkt

1. På sidan **Alla faktureringsscheman** skapar du ett faktureringsschema.
2. Om artikeln ännu inte har ställts in att använda ej fakturerad intäkt markerar du kryssrutan **Ej fakturerad intäkt** på faktureringsschemaraden.
3. Ange alternativet **Ej fakturerad intäkt** till **Ja**. Granska och redigera sedan ej fakturerad intäkt, rabatt och motkonto för ej fakturerad intäkt efter behov.
4. I faktureringsschema, under **Bearbetning av ej fakturerad intäkt**, välj **Skapa post i redovisningsjournal** för att skapa den ursprungliga journalposten för ej fakturerade intäkter. Det här steget måste slutföras innan faktureringsplanen faktureras.
5. När den ursprungliga journalposten har skapats väljer du **Generera faktura** för att skapa försäljningsorder och bokföra fakturor för faktureringsscheman.
6. När fakturorna har bokförts kan du granska granskningsinformationen på fliken **Förnyelser** på sidan **Alla faktureringsscheman**.

### <a name="milestone-billing"></a>Milstolpesfakturering

Milstolpefakturering fungerar med ej fakturerad intäkt under följande villkor:

- Om den överordnade milstolpeartikeln inte är fakturerad (kryssrutan **Ej fakturerad intäkt** har markerats) och de underordnade milstolpeartiklarna faktureras (kryssrutan **Ej fakturerad intäkt** är avmarkerad), måste start- och slutdatumen för den överordnade artikeln anges. Dessa datum används för att skapa den ursprungliga journalposten.
- Om den överordnade milstolpeartikeln inte är fakturerad (kryssrutan **Ej fakturerad intäkt** har avmarkerats) och de underordnade milstolpeartiklarna faktureras (kryssrutan **Ej fakturerad intäkt** är markerad), måste slutdatumen endast anges för den underordnade artikeln som du vill skala den ursprungliga journalposten för.

Varje underordnad milstolpeartikel kan bearbetas separat. Slutdatumen kan anges när du är klar att skapa den ursprungliga journalposten.

> [!NOTE]
> Om den ursprungliga journalposten för den överordnade eller underordnade milstolpeartikeln redan har skapats, eller om en faktura har skapats, kan start- och slutdatumen inte redigeras.

### <a name="unbilled-revenue-with-straight-line-deferrals"></a>Ej fakturerad intäkt med linjära periodiseringar

Om du vill använda ej fakturerad intäkt med linjära periodiseringstidsplaner följer du dessa steg.

1. På sidan **Alla faktureringsscheman** skapar du ett faktureringsschema.
2. Lägg till en artikel i faktureringsschemaraderna.
3. Välj **Periodiseringar** för raden.
4. Följ dessa steg på sidan **Transaktionsperiodisering**:

    1. Ge alternativet **Uppskjutet** värdet **Ja**.
    2. Ändra konton efter behov.
    3. I avsnittet **Tidsplan**, välj **Linjär** och redigera andra värden efter behov.
    4. Välj **OK**.

5. Välj **Ej fakturerad intäkt** för raden och gör så här:

    1. Ange alternativet **Ej fakturerad intäkt** till **Ja**.
    2. Välj konton som ska användas för intäkten, rabatt och motkonto för intäkt.

6. I faktureringsschema, under **Bearbetning av ej fakturerad intäkt**, välj **Skapa en post i redovisningsjournal**. Alternativt kan du använda sidan **Massbearbetning av ej fakturerad intäkt** för att skapa journalposten.
7. Periodiseringsschemat skapas. Du kan granska detaljerna på sidan **Alla periodiserade tidsplaner**. När periodiseringstidsplanen har skapats kan du redigera olika värden för radartikeln i faktureringsplanen. Du kan till exempel redigera enhetspris, kvantitet eller datum.

### <a name="unbilled-revenue-with-event-based-deferrals"></a>Ej fakturerad intäkt med händelsebaserade uppskjutningar

Om du vill använda ej fakturerad intäkt med händelsebaserade periodiseringstidsplaner följer du dessa steg.

1. På sidan **Alla faktureringsscheman** skapar du ett faktureringsschema.
2. Lägg till en artikel i faktureringsschemaraderna.
3. Välj **Periodiseringar** för raden.
4. Följ dessa steg på sidan **Transaktionsperiodisering**:

    1. Ge alternativet **Uppskjutet** värdet **Ja**.
    2. Ändra konton efter behov.
    3. I avsnittet **Schema**, välj **Händelsebaserad**, **Mall**, **Allokeringstyp** och **Utgångskonto**.
    4. Välj **OK**.

5. Välj **Ej fakturerad intäkt** för raden och gör så här:

    - Ange alternativet **Ej fakturerad intäkt** till **Ja**.
    - Välj konton som ska användas för intäkten, rabatt och motkonto för intäkt.

6. I faktureringsschema, under **Bearbetning av ej fakturerad intäkt**, välj **Skapa en post i redovisningsjournal**. Alternativt kan du använda sidan **Massbearbetning av ej fakturerad intäkt** för att skapa journalposten.
7. Periodiseringsschemat skapas. Du kan granska detaljerna på sidan **Alla periodiserade tidsplaner**. När periodiseringstidsplanen har skapats kan du redigera olika värden för radartikeln i faktureringsplanen. Du kan till exempel redigera enhetspris, kvantitet eller datum. Periodiseringstidsplanen beräknas om baserat på de nya värdena.

Fördelningarna beräknas om baserat på den allokeringstyp som valts (**Procent**, **Slutförandeprocent** eller **Lika med belopp**). För **Variabla belopp** fördelningen räknas om baserat på den procentuella ekvivalenten av utgångsvärdet för händelsen. Det ursprungliga enhetspriset betalas till 100,00 $ och procent av det ursprungliga värdet 55,00 $ (55 procent). Om enhetspriset ändras till ett 200,00 $ blir det rörliga beloppet för händelsen 110,00 $ (fortfarande 55 procent).

> [!NOTE]
> Om raderna för periodiseringstidsplan har identifierats går det inte att redigera radartikeln i faktureringsplanen. Om du vill redigera radartikeln måste du först återföra de kända raderna. Fakturaschemaraden kan sedan uppdateras.

### <a name="unbilled-revenue-and-top-billing"></a>Ej fakturerad intäkt och högsta fakturering

Ett faktureringsschema anges för tre år och fakturorna faktureras årligen under en treårsperiod. Hela kontraktsbeloppet registreras på det ej fakturerat intäktskonto som årliga fakturor skapas från. Motkontot är intäktskontot eller konto för periodiserad intäkt

Observera att de högsta fakturerings- och ej fakturerade intäkterna inte fungerar tillsammans, eftersom avstämningsproblem kan inträffa i redovisningen. Till exempel sidan **Konfiguration av artikelgrupp**, artikelgrupp A ställs in så att fältet **Antal övre rader** anges till **2**. På sidan **Faktureringsscheman** läggs tre artiklar till. Alla tre artiklarna hör till artikelgrupp A. När den ursprungliga journalposten skapas för funktionen för ej fakturerad intäkt bearbetas beloppet för alla tre artiklarna på det ej fakturerade kontot. När fakturan för faktureringsplanen skapas inkluderas bara beloppen för de två bästa artiklarna. Därför matchar fakturabeloppet inte det belopp som bearbetades på kontot för ej fakturerade intäkter och avstämningsproblem sker i redovisningen.

Om du vill använda ej fakturerade intäkter, lämna sidan **Konfiguration av artikelgrupp** tom eller ställ in alla artikelgrupper som tomt, eller ställ in alla artikelgrupper så att fältet **Antal övre rader** anges till **0** (noll). Om du vill använda den översta faktureringen finns inga ej fakturerade intäktsåtgärder tillgängliga.

### <a name="examples"></a>Exempel

Från och med version 10.0.27 finns ett nytt konto när ej fakturerade intäkter används. När den ursprungliga processen **Skapa journalpost** bokförs görs krediten på ett nytt motkonto för ej fakturerad intäkt. Detta konto används i stället för intäktskontot, eftersom samma värde måste återföras när faktureringsschemat faktureras. Om växelkurser eller avrundningsdifferenser uppstår kan beloppen som beräknas under processen **Generera faktura** vara olika. Detta beteende säkerställer att nettobeloppet för kontona är 0 (noll).

I det här exemplet visas hur du använder ej fakturerade intäkter för att redovisa hela beloppet för ett kontrakt i balansräkningen som ej fakturerade intäkter. Den andra sidan av posten är motbokningen av ej fakturerade intäkter. När du fakturerar kunden återförs den ej fakturerade intäkten och motbokningen av ej fakturerade intäkter. Intäktsredovisningen sker antingen vid faktureringen eller i enlighet med periodiseringsschemat som har ställts in.

#### <a name="assumptions"></a>Antaganden

- Den 1 januari det aktuella året signerar en kund ett treårigt kontrakt för 390 $.
- Kontraktet innehåller två delar: licenser och ett underhållsavtal.
- Försäljningspriset för licensavgiften betalas 300 $ och kunden faktureras innan den 100 $ 1 januari varje kontraktsår. Licensavgiften på 300 $ tas som intäkt när avtalet undertecknas.
- Försäljningspriset för underhållsavgiften betalas 90 $ och kunden faktureras innan den 30 $ 1 januari varje kontraktsår. Underhållsavgiften på 90 $ kommer att periodiseras och 2,50 $ redovisas varje månad under kontraktets livstid.
- Kunden faktureras i 130 $ i början (1 januari) av vart och ett av kontraktets tre år.

#### <a name="steps"></a>Steg

1. Ange de två frisläppta artiklarna som ej fakturerade artiklar. Använd sidan **Inställningar för ej fakturerad intäkt** för att ställa in artiklar och konton som använder ej fakturerade intäkter.
2. I det här exemplet uppskjuts underhållsavgiften. Artikeln kräver en periodiseringsmall ställs in på sidan **periodiseringsmallar**. Mallen har en periodfrekvens **månad** och en redovisningsperiod på 36 månader. Därför är intäkten per månad 2,50 $.
3. På sidan **Artiklar som har periodiserats som standard** ställ in fältet **Underhållsfri** till **Periodiserbar artikel**. Det här steget och nästa innebär att den underhållsfria artikeln periodiseras när den säljs eller inkluderas i ett faktureringsschema.
4. Välj **Standardinställningar för periodisering** \> **Mall** och lägg till artikeln för underhållsavgiften och den linjära mallen från steg 2. Den underhållsfria artikeln länkas till ett 36-månaders periodiseringsschema.
5. Skapa ett faktureringsschema som innehåller de två ofakturerade artiklarna. Faktureringsschemat för kontraktet ställs in med följande artiklar.

    | Objekt | Startdatum | Slutdatum | Belopp | Faktureringsfrekvens | Periodiseringsartikel | Ej fakturerad intäkt | Beskrivning |
    |---|---|---|---|---|---|---|---|
    | Licens | 01 januari, CY | 31 december CY+2 | 100,00 $ | Årligen | Nej | Ja | Kunden kommer att faktureras 100,00 $ varje år. Summan 300,00 $ kommer i förväg att registreras som ej fakturerade intäkter i balansräkningen och som intäkt för resultaträkningen. Varje faktura minskar det ej fakturerade beloppet. |
    | Bibehåll | 01 januari, CY | 31 december CY+2 | 30,00 $ | Årligen | Ja | Ja | Kunden kommer att faktureras 30,00 $ varje år. Summan 90,00 $ kommer i förväg att registreras som ej fakturerade intäkter och periodiserad intäkt i balansräkningen. Varje faktura minskar det ej fakturerade beloppet. Den periodiserade intäkten redovisas månadsvis under 36 månader. |

6. På sidan **Alla faktureringsscheman** använder du processen **Skapa journalpost** om du vill bokföra kontraktsvärdet i balansräkningen som ej fakturerade intäkter.

Två journalposter skapas, en för varje rad i faktureringsschemat.

| Konto för ej fakturerad intäkt | Motkonto för ej fakturerad intäkt | Debetbelopp | Kreditbelopp |
|---|---|---|---|
| Konto för ej fakturerad intäkt | | 300,00 $ | |
| | Motkonto för ej fakturerad intäkt | | 300,00 $ |

| Konto för ej fakturerad intäkt | Uppskjuten intäkt | Debetbelopp | Kreditbelopp |
|---|---|---|---|
| Konto för ej fakturerad intäkt | | 90,00 $ | |
| |Uppskjuten underhållsintäkt | | 90,00 $ |

Den första journalposten bokförs på ett motkonto för ej fakturerad intäkt och den andra bokförs på ett konto för periodiserad intäkt. Om faktureringsraden har både ej fakturerad intäkt och periodiserad intäkt används kontot för periodiserad intäkt, inte motbokningen av ej fakturerade intäkter. Kontraktet kräver att fakturan för kunden skapas i början av varje år. Använd processen **Generera faktura** om du vill skapa fakturan. När fakturan skapas skapas följande journalposter.

| Huvudkonto | Konto för ej fakturerad intäkt | Debetbelopp | Kreditbelopp |
|---|---|---|---|
| Motbokning av ej fakturerade intäkter | | 100,00 $ | |
| | Konto för ej fakturerad intäkt | | 100,00 $ |
| Kundreskontra | | 100,00 $ | |
| | Intäktskonto | | 100,00 $ |

| Huvudkonto | Konto för ej fakturerad intäkt | Debetbelopp | Kreditbelopp |
|---|---|---|---|
| Konto för uppskjuten underhållsintäkt | | 30,00 $ | |
| | Konto för ej fakturerad intäkt | | 30,00 $ |
| Kundreskontra | | 30,00 $ | |
| | Konto för uppskjuten underhållsintäkt | | 30,00 $ |

Samma journalpost skapas av fakturor som bokförs i början av de kommande två åren. Nettobeloppet för kontot för uppskjuten intäkt är 0 (noll), eftersom det inte finns några avrundnings- eller valutakursdifferenser. Den uppskjutna intäkten måste återföras exakt på samma sätt som den krediterades under processen **Skapa journalpost**. Eftersom intäkten fortfarande periodiseras och kommer att redovisas senare, sker krediten till konto för periodiserad intäkt igen.

I det sista steget skapas ursprungliga redovisningsjournalposten varje månad för att redovisa intäkten för den uppskjutna underhållsavgiften. Journalposten kan skapas på sidan **Bearbetning av redovisning**. Du kan också skapa den genom att välja **Känna igen** för raderna på sidorna **Periodiseringsschema**.

| Konto för periodiserad intäkt | Intäktskonto | Debetbelopp | Kreditbelopp |
|---|---|---|---|
| Uppskjuten underhållsintäkt | | 2,50 $ | |
| | Underhållsintäkt | | 2,50 $ |

Den här journalposten skapas varje gång igenkänningsprocessen körs för den här periodiserade artikeln (totalt 36 gånger).

#### <a name="short-term-fixed-year"></a>Kortfristiga fast år

Du kan använda ej fakturerade intäkter tillsammans med den kortsiktiga funktionen genom att ställa in fältet **Kortfristig ej fakturerad** på sidan **Faktureringsparametrar för återkommande kontrakt**. Följande exempel visar de beräkningar som görs när ej fakturerade intäkter används tillsammans med metoden **Fast år** kortfristig ej debiterad.

Ett faktureringsschema med följande kriterier skapas:

- **Startdatum:** 1 juni 2020
- **Slutdatum:** 31 december, 2021
- **Enhetspris:** 100 $
- **Frekvens:** Månadsvis

På sidan **Alla faktureringsscheman** skapas den inledande journalposten av processen **Skapa journalpost**. Aktuella kortfristiga och långsiktiga belopp beräknas på följande sätt:

- **Aktuellt belopp för kortfristig icke-fakturerad intäkt:** 700 $
- **Aktuellt belopp för långfristig icke-fakturerad intäkt:** 1 200 $

Fakturan skapas för faktureringsperioden från 1 juni 2020 till 30 november 2020. Aktuella kortfristiga och långsiktiga belopp beräknas på följande sätt:

- **Aktuellt belopp för kortfristig icke-fakturerad intäkt:** 100 $
- **Aktuellt belopp för långfristig icke-fakturerad intäkt:** 1 200 $

Fakturan skapas för faktureringsperioden från 1 december 2020 till 31 december 2020. Aktuella kortfristiga och långsiktiga belopp beräknas på följande sätt:

- **Aktuellt belopp för kortfristig icke-fakturerad intäkt:** 1 200 $
- **Aktuellt belopp för långfristig icke-fakturerad intäkt** 0 $

#### <a name="short-term-rolling-periods"></a>Kortfristig: Rullande perioder

Du kan använda ej fakturerade intäkter tillsammans med den kortsiktiga funktionen genom att ställa in kortfristig ej debiterar metod på sidan **Faktureringsparametrar för återkommande kontrakt**. Följande exempel visar de beräkningar som görs när ej fakturerade intäkter används tillsammans med metoden **Rullande perioder** kortfristig ej debiterad.

Ett faktureringsschema med följande kriterier skapas:

- **Startdatum:** 1 juni 2020
- **Slutdatum:** 31 december, 2021
- **Enhetspris:** 100 $
- **Frekvens:** Månadsvis

På sidan **Alla faktureringsscheman** skapas den inledande journalposten av processen **Skapa journalpost**. Aktuella kortfristiga och långsiktiga belopp beräknas på följande sätt:

- **Aktuellt belopp för kortfristig icke-fakturerad intäkt:** 1 200 $
- **Aktuellt belopp för långfristig icke-fakturerad intäkt** 700 $

Fakturan skapas för faktureringsperioden från 1 juni 2020 till 30 november 2020. Aktuella kortfristiga och långsiktiga belopp beräknas på följande sätt:

- **Aktuellt belopp för kortfristig icke-fakturerad intäkt:** 1 200 $
- **Aktuellt belopp för långfristig icke-fakturerad intäkt** 100 $

Fakturan skapas för faktureringsperioden från 1 december 2020 till 31 december 2020. Aktuella kortfristiga och långsiktiga belopp beräknas på följande sätt:

- **Aktuellt belopp för kortfristig icke-fakturerad intäkt:** 1 200 $
- **Aktuellt belopp för långfristig icke-fakturerad intäkt** 0 $

### <a name="items-with-revenue-allocation"></a>Artiklar med intäktsallokering

Två artiklar med olika faktureringsfrekvenser läggs till i ett faktureringsschema. Både använder ej fakterade intäkter och periodiseringsbara artiklar.

- **Artikelnummer 1 000:** Surface Pro 128 GB

    - **Faktureringsfrekvens:** En gång
    - **Enhetspris:** 1 500 $
    - **Fristående försäljningspris:** 1 600 $
    - **Kontraktsintäkt:** 1 465,26 $

- **Artikelnummer S0021:** Försäkring som säljs tillsammans med artikelnummer 1000

    - **Faktureringsfrekvens:** Månad för 12 månader
    - **Enhetspris:** 20 $ per månad
    - **Fristående försäljningspris:** 25 $
    - **Kontraktsintäkt:** 264,74 $

Eftersom både artiklarna använder ej fakturerade intäkter och intäktsallokering är det totala kontraktsbeloppet på den förnyade raden 0 (noll). Kolumnen **Kontraktsintäkter** läggs till och visar kontraktsintäktsbeloppet.

I följande tabell visas den ursprungliga journalposten för artiklarna och fakturan.

| Konto för ej fakturerad intäkt | Konto för periodiserad intäkt | Debetbelopp | Kreditbelopp |
|---|---|---|---|
| **Artikel 1000 redovisningsjournal** | | | |
| Debitera konto för ej fakturerad intäkt (401250) | | 1 465,26 $ | |
| | Kreditera konto för periodiserad intäkt (250600) | | 1 465,26 $ |
| **Artikel 0021 redovisningsjournal** | | | |
| Debitera konto för ej fakturerad intäkt (401250) | | 274,74 $ | |
| | Kreditera konto för periodiserad intäkt (250600) | | 274,74 $ |
| **Faktura** | | | |
| | Kreditera konto för ej fakturerad intäkt | | 1 465,26 $ |
| | Kreditera konto för ej fakturerad intäkt | | 274,74 $ |
| Debitera AR-konto (130100) | | 1 488,16 $ | |

#### <a name="changes-to-the-billing-schedule-line-billing-detail-line-or-revenue-allocation"></a>Ändringar av raden i faktureringsplanen, en faktureringsdetaljrad eller intäktsallokering

När priset eller kvantiteten per enhet ändras måste beloppet för kontraktsintäkterna för varje artikel som ingår i intäktsallokeringen uppdateras. Därför beräknas journalposten om.

Enhetspriset för artikel 1000 ändras till exempel från 1 500 $ till 1 600 $. I det här fallet beräknas kontraktintäktsbeloppet automatiskt om till 1 549,47 $. Kontraktintäkten för artikel S0021 beräknas om 290,53 $.

När det ändrade bekräftas och utfästs återförs de ursprungliga journalposterna för båda artiklarna och nya journalposter skapas:

- **Artikel 1000:** Den ursprungliga journalposten på 1 465,26 $ har återförts. En ny journalpost för 1 549,47 $ skapas.
- **Artikel S0021:** Den ursprungliga journalposten på 274,74 $ har återförts. En ny journalpost för 290,53 $ skapas.

#### <a name="termination"></a>Uppsägning

Artikel S0021 har startdatumet januari 2020 och slutdatumet är december 2020, men avslutas i juni 2020. Kontraktintäktsbeloppet för båda artiklarna måste beräknas om:

- **Artikel 1000:** Kontraktintäkten beräknas om till 1 567,67 $.
- **Artikel S0021:** Kontraktintäkten beräknas om till 124,00 $.

En justeringsjournalpost skapas för raden som avslutas. Journalposten för raden som hör till samma MEA-nummer (system med flera element) återförs och en ny journalpost skapas:

- **Artikel 1000:** Den ursprungliga journalposten på 1 465,26 $ har återförts. En justeringsjournalpost för 1 549,47 $ skapas.
- **Artikel S0021:** Den ursprungliga journalposten på 274,74 $ har återförts. En ny journalpost för 124,00 $ skapas.
