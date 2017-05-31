---
title: Kolumndefinitioner i ekonomiska rapporter
description: "Den här artikeln innehåller information om kolumndefinitioner. En kolumndefinition är en rapportkomponent eller ett byggblock som definierar innehållet i kolumner i en rapport. Precis som raddefinitioner kan grundläggande kolumndefinitioner användas för flera rapporter."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter, Core
ms.custom: 106601
ms.assetid: 66e72a48-edab-4e9d-815f-596a1623c258
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ca82d24f591aaeb0d675716857cf94a4696785ad
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="column-definitions-in-financial-reports"></a>Kolumndefinitioner i ekonomiska rapporter

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om kolumndefinitioner. En kolumndefinition är en rapportkomponent eller ett byggblock som definierar innehållet i kolumner i en rapport. Precis som raddefinitioner kan grundläggande kolumndefinitioner användas för flera rapporter.

<a name="create-and-modify-a-column-definition"></a>Skapa och ändra en kolumndefinition
-------------------------------------

En kolumndefinition kan innehålla två till 255 kolumner.

### <a name="create-a-column-definition"></a>Skapa en kolumndefinition

1.  I Report Designer, i navigeringsfönstret klickar du på **Kolumndefinitioner**.
2.  På menyn **Arkiv** klickar du först på **Ny** och sedan på **Kolumndefinition**.
3.  Lägg till innehållet i kolumndefinitionen.

### <a name="open-a-column-definition"></a>Öppna en kolumndefinition

1.  I Report Designer, i navigeringsfönstret klickar du på **Kolumndefinitioner**.
2.  Dubbelklicka på en kolumndefinition för att öppna den.

### <a name="add-a-column-to-a-column-definition"></a>Lägg till en kolumn i en kolumndefinition

1.  I Rapportdesignern, klicka på **Kolumnddefinitioner** och öppna kolumndefinitionen för att ändra.
2.  Markera kolumnen där en ny kolumn ska infogas.
3.  I menyn **Redigera**, klicka på **Infoga kolumn**. Den nya kolumnen visas till vänster om kolumnen som du har valt.

### <a name="delete-a-column-from-a-column-definition"></a>Ta bort en kolumn från en kolumndefinition

1.  I Rapportdesignern, klicka på **Kolumnddefinitioner** och öppna kolumndefinitionen för att ändra.
2.  Markera en kolumn som du vill ta bort.
3.  I menyn **Redigera**, klicka på **Ta bort kolumn**.

## <a name="contents-of-a-column-definition"></a>Innehåll i en kolumndefinition
En kolumndefinition omfattar följande information:

-   En kolumn för beskrivningar av raddefinitionen
-   Beloppkolumner som visar data från ekonomiska data, ett Microsoft Excel-kalkylblad eller beräkningar som baseras på andra data i kolumndefinitionen
-   Formateringskolumner
-   Attributkolumner

Den här informationen visas i följande områden i kolumndefinitionen:

-   Kolumndefinitionens huvudområde innehåller den rubriktext och formatering som visas i rapporten. En rubrik kan gälla för en enskild datakolumn, sträcka sig över flera kolumner eller användas på kolumner på villkorsbasis. Kolumndefinitionen kan innehålla så många kolumnrubrikrader som du behöver. **Obs!** Kolumnrubriker gäller för varje datakolumn i rapporten. Rapportrubriker gäller för hela rapporten. Du definierar rapportrubriker på fliken **Sidhuvud och sidfot** i rapportdefinitionen.
-   Kolumndetaljrader är raderna under rubrikraderna i kolumndefinitionen. Kolumndetaljrader definierar informationen som inkluderas i rapporten. Följande tabeller listar och beskriver kolumndetaljraderna.

    | Namn på kolumndetaljrad                                                | Beskrivning                                                                                            |
    |-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
    | Kolumntyp                                                           | Ange typ av data i kolumnen (obligatoriskt).                                                     |
    | Bokkod/attributkategori                                          | Ange information om ekonomiska data för kolumner av typen **FD** och **ATTR**.                       |
    | Räkenskapsårperiod täcks                                    | Ange information om ekonomiska data för kolumner av typen **FD**.                                     |
    | Formel                                                               | Ange en beräkningsformel för kolumner av typen **CALC**.                                        |
    | Kolumnbredd Ytterligare blanksteg innan kolumn Åsidosättning av format Utskriftskontroll | Ange särskilda formatalternativ.                                                                        |
    | Kolumnbegränsningar                                                   | Begränsa data.                                                                                         |
    | Rapporteringsenhet                                                        | Begränsa kolumnen så att den endast visar data för den angivna rapportenheten.                      |
    | Valuta Visa valutafilter                                      | Formatera valuta.                                                                                       |
    | Dimensionsfilter                                                      | Ange ett filter för att begränsa data till vissa ekonomiska datarapportenheter.                           |
    | Attributfilter                                                      | Ange ett filter för att begränsa de ekonomiska data.                                                       |
    | Slutdatum Startdatum                                                   | Begränsa de ekonomiska data till specifika datum.                                                         |
    | Motivering                                                         | Vänsterjustera, centrera eller högerjustera beskrivningstexten som anges i raddefinitionen. |

## <a name="column-restrictions-in-a-column-definition"></a>Kolumnbegränsningar i en kolumndefinition
Du kan använda kolumnbegränsningar för att ange hur en kolumndefinition använder data eller beräknar information. Du kan även begränsa en rapportkolumn till en viss enhet eller för specifika datum. **Obs!** En kod för **Kolumnbegränsning** åsidosätter alla motstridiga inställningar som används i raddefinitionen.

### <a name="column-restrictions-cell"></a>Kolumnbegränsningscell

Cellen **Kolumnbegränsningar** kan inkludera koder som begränsar eller döljer information som till exempel radformatering, detaljer och belopp för den kolumnen.

#### <a name="add-a-column-restriction-in-a-column-definition"></a>Lägg till en kolumnbegränsning i en kolumndefinition

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på cellen **Kolumnbegränsningar** för att begränsa.
3.  I dialogrutan **Kolumnbegränsningar** markera en eller flera koder i listan och klicka på **OK**.

### <a name="column-restriction-codes"></a>Kolumnbegränsningskoder

Följande register beskriver kolumnbegränsningskoderna.

| Kolumnbegränsningskod | Beskrivning                                                                                                                                                                                                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SU                      | Dölj understreck för en kolumn där antingen ett understreckskommando (**---**) eller ett dubbelt understreckskommando (**===**) anges i raddefinitionen. Du kan till exempel välja att inte understryka belopp som produceras av en procentsatsberäkning.                                                                        |
| ST                      | Undertryck summor så att endast information visas i kolumnen (exempelvis en statistisk kolumn).                                                                                                                                                                                                                                      |
| SD                      | Undertryck detaljer så att endast raderna **TOT** och **CAL** (från raddefinitionen) visas i kolumnen.                                                                                                                                                                                                                              |
| DR                      | Begränsa beloppen i en**FD**-kolumn till debetbelopp.                                                                                                                                                                                                                                                                              |
| CR                      | Begränsa beloppen i en **FD**-kolumn till kreditbelopp.                                                                                                                                                                                                                                                                             |
| ADJ                     | Begränsa beloppen i kolumnen till periodjusteringsbelopp, om dessa belopp är tillgängliga.                                                                                                                                                                                                                                        |
| XAD                     | Begränsa beloppen i kolumnen så att periodjusteringsbelopp exkluderas.                                                                                                                                                                                                                                                     |
| PT                      | Begränsa beloppen i kolumnen, så att endast bokförda transaktioner inkluderas, om dessa transaktioner är tillgängliga.                                                                                                                                                                                                                 |
| UPT                     | Begränsa beloppen i kolumnen, så att endast ej bokförda transaktioner inkluderas, om dessa transaktioner är tillgängliga. **Obs!** Alla dataleverantörer stödjer inte ej bokförda transaktioner. Mer information finns i [dataintegreringsguiden](http://go.microsoft.com/fwlink/?LinkID=162565) för ditt Microsoft Dynamics ERP-system. |

### <a name="restrict-a-column-to-a-reporting-unit"></a>Begränsa en kolumn i en rapportenhet

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på cellen **Rapportenhet** för kolumnen för att begränsa.
3.  I diaglogrutan **Val av rapporteringsenhet**, i listan **Rapporteringsträd**, välj ett träd.
4.  Expandera eller dölj listan över enheter, välj en rapportenhet och klicka sedan på **OK**.

## <a name="format-column-headers"></a>Formatera kolumnrubriker
Du kan lägga till, ändra och ta bort rubriker som anges överst i kolumnerna i en rapport. Du kan även konfigurera villkorsstyrda omfatta kolumnrubrik som baseras på fältet **Period** från kolumndefinitioner och fältet **Basperiod** från rapportdefinitioner. Funktionen basperiod hjälper dig att spara tid när du skapar rullande prognosrapporter.

### <a name="create-and-manage-column-headers"></a>Skapa och hantera kolumnrubriker

Du kan använda dialogrutan **Kolumnrubrik** för att lägga till, ändra och ta bort rubriker som anges överst i kolumnerna i en rapport. I tabellen nedan beskrivs fälten i dialogrutan **Kolumnrubrik**.

| Fält                 | Beskrivning                                                                                                                                                                                                                                                                                                              |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kolumnrubriktext    | Texten visas i kolumnrubriken. Du kan ange text direkt i det här fältet eller klicka på **Infoga autotext** om du vill välja ett alternativ som uppdaterar kolumnrubriken varje gång som rapporten genereras. Klicka på **Infoga autotext** igen för att inkludera flera autotextkoder och klicka sedan på en annan kod i listan. |
| Formatalternativ        | Formatera en kolumnrubrik, till exempel ruta eller understrykning.                                                                                                                                                                                                                                                           |
| Fördela från Fördela till | Definiera kolumnen eller kolumnerna som rubriktexten gäller för.                                                                                                                                                                                                                                                            |
| Motivering         | Ange hur kolumnrubriktexten ska justeras för kolumnen eller intervallet av kolumnerna som anges i fälten **Fördela från** och **Fördela till** .                                                                                                                                                               |

### <a name="create-a-column-header"></a>Skapa en kolumnrubrik

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på en rubrikcell.
3.  Ange kolumnrubriktexten i dialogrutan **Kolumnrubrik**. Alternativt kan du klicka på **Infoga autotext** och välja ett alternativ.
4.  Välj ett format för rubriken i fältet **Formatalternativ**.
5.  Ange bokstaven i kolumnen som kolumnrubriken ska börja med i fältet **Fördela från**. Ange bokstaven i kolumnen som kolumnrubriken ska sluta med i fältet **Fördela till**.
6.  Välj om kolumnhuvudtexten ska vänsterjusteras, centreras eller högerjusteras i **Motivering**.
7.  Klicka på **OK**.

### <a name="add-a-column-header-row"></a>Lägga till en kolumnrubrikrad

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Välj en cell i rubrikraden.
3.  I menyn **Redigera**, klicka på **Infoga rad**. Den nya raden läggs till efter den rad som du valde i steg 2. **Obs!**Om du har fyra eller fler rader för rapportrubriker i en rapport, kommer rubrikerna att överlappa varandra när rapporten exporteras till ett Excel-kalkylblad. Öka den översta marginalen i rapportdefinitionen om du vill visa alla rubriker i rapporten.

### <a name="delete-a-column-header-row"></a>Ta bort en kolumnrubrikrad

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Välj cellen som du vill ta bort i rubrikraden.
3.  I menyn **Redigera**, klicka på **Ta bort rad**.

### <a name="create-an-automatically-generated-header"></a>Skapa en automatiskt genererad rubrik

Rapportutformaren kan skapa kolumnrubriker automatiskt baserat på autotextkoder. Autotextkoder är variabler som uppdateras varje gång som en rapport genereras. Alla kolumnrubriker kan innehålla dessa koder för att ange rapportinformation som kan variera, t.ex. datum eller periodnummer. Därför kan du använda en kolumndefinition för flera rapportdefinitioner, tidsperioder och rapportträd. Eftersom autotextkoder hänvisar till kalenderinformationen från detaljraderna i kolumndefinitionen, stöds de endast för kolumnerna **CALC**, **FD** och **WKS**. Sättet som en autotextkod visas i kolumnrubriken inverkar på hur den informationen visas i rapporten. I dialogrutan **Kolumnrubrik** visas autotextkoderna när gemener och versaler blandas. Därför visas texten i rapporten när gemener och versaler blandas. Under ett vanligt kalenderår förvandlar exempelvis **@CalMonthLong** månaden **7** till **juli**. Om namnet på månaden ska vara i versaler (till exempel **JULI**) anger du autotextkoden i versala tecken i fältet **Kolumnrubriktext**. Ange till exempel **@CALMONTHLONG**. Du kan blanda koder och text. Till exempel anger du följande rubriktext: **Perioden @FiscalPeriod-@FiscalYear från @StartDate till @EndDate**. Rapportrubriken som skapas liknar följande text: **Period 1-02 från 01/01/02 till 01/31/02**. **Obs!** Formatet för en del av texten, till exempel det långa datumformatet, beror på dina regionala inställningar på Dynamics 365 for Operations-servern. För att ändra dessa inställningar, klicka på knappen **Starta**, klicka på **Kontrollpanelen** och klicka sedan på **Region och språk**. Följande tabeller listar de tillgängliga autotextalternativen för kolumnrubriker.

| Autotextalternativ och kod                | beskrivning                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Månadsnamn (@CalMonthLong)              | Skriv ut namnet på den aktuella månaden i kolumnrubriken. Om du väljer att avrunda beloppen i rapporten till tusental, miljoner eller miljarder, eller om du har ställt in kolumnbredden i rapporten till färre än nio tecken, förkortas namnet på månaden till de första tre tecknen. |
| Förkortat månadsnamn (@CalMonthShort) | Skriv ut det förkortade månadsnamnet för den valda räkenskapsperioden.                                                                                                                                                                                                                          |
| Periodnummer (@FiscalPeriod)           | Skriv ut den numeriska formen för räkenskapsperioden som identifieras för den kolumnen. Om kolumnen omfattar flera perioder, skriv ut den senaste perioden i intervallet.                                                                                                                                   |
| Periodbeskrivning (@FiscalPeriodName)  | Skriv ut beskrivningen av räkenskapsperioden som identifieras i de ekonomiska data.                                                                                                                                                                                                                    |
| Räkenskapsår (@FiscalYear)               | Skriv ut räkenskapsåret för kolumnen i numerisk form.                                                                                                                                                                                                                                            |
| Kalenderår (@CalYear)                | Skriv ut kalenderåret för kolumnen i numerisk form.                                                                                                                                                                                                                                          |
| Startdatum (@StartDate)                 | Skriv ut startdatumet för kolumnen.                                                                                                                                                                                                                                                             |
| Slutdatum (@EndDate)                     | Skriv ut slutdatumet för kolumnen.                                                                                                                                                                                                                                                               |
| Enhetsnamn i trädet (@UnitName)         | Om du begränsar en kolumn till en viss enhet av rapportträdet, skriver du ut enhetsnamnet i kolumnrubriken.                                                                                                                                                                                     |
| Enhetsbeskrivning (@UnitDesc)            | Om du begränsar en kolumn till en viss enhet av rapportträdet, skriver du ut enhetsbeskrivningen i kolumnrubriken.                                                                                                                                                                              |
| Kod för bok (@BookCode)                   | Skriv ut bokkoden som anges i kolumnen.                                                                                                                                                                                                                                             |
| Tom rad (@Blank)                     | Infoga en tom rad i kolumnrubriken.                                                                                                                                                                                                                                                       |

### <a name="create-a-conditional-spanning-header"></a>Skapa en villkorsstyrd omfattande rubrik

Villkorsstyrda omfattande rubriker kan omfatta flera kolumner som baseras på specifika perioddatum. Om du till exempel har en budgetrapport för räkenskapsåret och vill visa de verkliga budgetarna för föregående månader tillsammans med de projekterade budgetarna för framtida månader, kan du använda en villkorsstyrd omfattande rubrik för att automatiskt uppdatera rapportrubriken. Var medveten om följande situationer när du skapar en villkorsstyrd omfattande rubrik:

-   Alla stoppvillkor (fältet **Fördela till**) som matchas innan ett startvillkor (fältet**Fördela Från**) ignoreras. Till exempel kolumn B har det fördelade villkoret angivet som BASE+1 till BASE, BASE i kolumn C, och BASE+1 är i kolumn D. I detta fall ignoreras stoppvillkoret i kolumn C, och utskriften av rubriken startar i kolumn D.
-   Om du anger kolumnrubriker som överlappar varandra, kommer de att överlappas när de skrivs ut i rapporten. Rapporten genereras, men följande varning visas i fältet **Rapportköstatus**: ""Kolumnrubriker som använder bas (Base) överlappar andra kolumnrubriker och medföra överlappande text." Exempelvis är rubrikdefinitionen i kolumn B lika med B till BASE +1, och rubrikdefinitionen för kolumn D är BASE +1 till F. I det här fallet skrivs rubrikerna ovanpå varandra och är oläsliga. Så snart BAS används i definitionen **Fördela från/fördela till** ska du se till att visa rapporten som skapas, för att se om rubrikerna överlappas.
-   Om du anger i BASE den fördelade definitionen i en kolumn för Ingen utskrift (**NP**) kommer den att ignoreras, oavsett vad som har definierats i kolumndefinitionen. I grunden är detta scenario detsamma som att inte skapa en kolumnrubrikdefinition.
-   För villkorsstyrda utskriftskolumner (**P&lt;B**, **P&gt;=B**) uppför sig villkorsstyrda omfattande rubriker som alla vanliga kolumnrubrikdefinitioner. Om till exempel villkoret är falskt, startar en efterföljande kolumn som matchar det fördelade villkoret en utskrift av rubriken.

#### <a name="create-a-conditional-spanning-header"></a>Skapa en villkorsstyrd omfattande rubrik

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på en rubrikcell.
3.  Ange kolumnrubriktexten i dialogrutan **Kolumnrubrik**. Alternativt kan du klicka på **Infoga autotext** och välja ett alternativ.
4.   Välj en formateringsstil för rubriken i fältet **Formatalternativ**.
5.  Ange en period i förhållande till basperioden som har angetts, när rapporten genereras. I fälten **Fördela från** och **Fördela till** anger du ett av följande värden: **BASE**, **BASE-X** eller **BASE+X** där X är antalet perioder från basperioden. Om du till exempel anger **BASE** i fältet **Fördela från**börjar den villkorsstyrda omfattande kolumnrubriktexten i kolumnrubriken där rapportdefinitionens värde är lika med kolumndefinitionens **Basperiod**-värde är lika med kolumndefinitionens **Period**-värde. Den avslutas i den kolumnen som anges i fältet **Fördela till**. Om fördelningen är BASE till M, och rapportdefinitionens **Basperiod**-värde är **4**, börjar och slutar rubriken i den kolumn där perioden anges som **4** och slutar i kolumn H. Rubriker stoppar och startar endast vid utskrift av kolumner.
6.  Välj om kolumnhuvudtexten ska vänsterjusteras, centreras eller högerjusteras i **Motivering**.
7.  Klicka på **OK**.

#### <a name="example-of-a-conditional-spanning-header"></a>Exempel på en villkorsstyrd omfattande rubrik

Phyllis skapar en rapport för en dynamisk sexmånadersprognos. Hon vill att ordet "Aktuell" ska skrivas ut över kolumnerna, som innehåller aktuella data och att ordet "Budget" ska skrivas ut över kolumner som innehåller budgetprognoser. Varje månad som rapporten körs finns det en till aktuell kolumn och en mindre budgetkolumn. Även om Phyllis kan ändra kolumndefinitionen manuellt varje gång som rapporten genereras för att justera rubrikerna bestämmer hon, i syfte att spara tid och insats, sig för att skapa villkorsstyrda omfattande rubriker som automatiskt kommer att skapa rubriker över motsvarande kolumner varje gång som rapporten körs. Phyllis öppnar Report Designer, klickar på **Kolumndefinition** i navigeringsfönstret och öppnar kolumndefinitionen för rapporten. Hon anger följande information. Basperioden i rapportdefinitionen är 4.

|                     | A    | B             | C             | D             | E             | F             | G             | H             | I             | J             | k             | S             | M             |
|---------------------|------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|
| Rubrik 1            |      | Faktisk        | Budget        |               |               |               |               |               |               |               |               |               |               |
| Rubrik 2            |      | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong |
| Rubrik 3            |      |               |               |               |               |               |               |               |               |               |               |               |               |
| Kolumntyp         | DESC | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            |
| Bokkod/attribut |      | AKTUELL        | BUDGET2012    | AKTUELL        | BUDGET2012    | AKTUELL        | BUDGET2012    | AKTUELL        | BUDGET2012    | AKTUELL        | BUDGET2012    | AKTUELL        | BUDGET2012    |
| Räkenskapsår         |      | BAS          | BAS          | BAS          | BAS          | BAS          | BAS          | BAS          | BAS          | BAS          | BAS          | BAS          | BAS          |
| Period              |      | 1             | 1             | 2             | 2             | 3             | 3             | 4             | 4             | 5             | 5             | 6             | 6             |
| Täckta perioder     |      | PERIODISK      | PERIODISK      | PERIODISK      | PERIODISK      | PERIODISK      | PERIODISK      | PERIODISK      | PERIODISK      | PERIODISK      | PERIODISK      | PERIODISK      | PERIODISK      |
| Kolumnbredd        | 30   | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            |
| Utskriftskontroll       |      | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        |

Phyllis dubbelklickar på en kolumrubrikcell för att öppna dialogrutan **Kolumnrubrik** där hon anger följande information.

| Fält              | Värde                 |
|--------------------|-----------------------|
| Kolumnrubriktext | Faktiskt                |
| Infoga autotext    | Inget val har gjorts. |
| Formatera alternativ     | Ruta                   |
| Motivering      | Inget val har gjorts. |
| Fördela från        | G                     |
| Fördela till          | BAS                  |
| Budgetrubrik      | Kolumnen BASE+1 till slut  |

När Phyllis är klar med att ange information, klickar hon på **OK**. Sedan dubbelklickar hon på kolumrubrikcellen i kolumn C för att öppna dialogrutan **Kolumnrubrik** där hon anger följande information.

| Fält              | Värde                 |
|--------------------|-----------------------|
| Kolumnrubriktext | Budget                |
| Infoga autotext    | Inget val har gjorts. |
| Formatera alternativ     | Ruta                   |
| Motivering      | Inget val har gjorts. |
| Fördela från        | C                     |
| Fördela till          | BASE+2                |

Nu när denna rapport skapas kommer ordet "Aktuell" att skrivas ut över kolumnerna, som innehåller aktuella data och att ordet "Budget" kommer att skrivas ut över kolumner som innehåller budgetprognoser. Dessutom kommer antalet kolumner att justeras varje månad.

## <a name="apply-column-justification"></a>Använd kolummotivering.
Cellen **Motivering** används för att tillämpar motivering av formatering till en beskrivningskolumn i en rapport. Det här alternativet påverkar endast kolumnbeskrivningarna, inte de faktiska värdena.

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på cellen **Motivering**.
3.  Välj ett av följande värden från listan:
    -   **Ingen** – Ingen motivering tillämpas.
    -   **Vänster** – Vänsterjustera kolumnbeskrivningarna.
    -   **Centrera** – Centrera kolumnbeskrivningarna.
    -   **Höger** – Högerjustera kolumnbeskrivningarna.

## <a name="add-special-formatting-options"></a>Lägg till speciella formateringsalternativ
I kolumndefinitionen tillämpar kolumndetaljraderna för formatering en viss formatering på valda kolumner. Även om några av alternativen **Utskriftskontroll** och **Kolumnbegränsningar** är specifika för **FD**-kolumner, gäller de flesta alternativen alla kolumntyper. Den formatering som anges i kolumndefinitionen åsidosätter den formatering som anges i rapportdefinitionen. Men den formatering som anges i raddefinitionen åsidosätter den formatering som anges i kolumndefinitionen. Följande rader anses vara formateringsrader:

-   Kolumnbredd
-   Ytterligare mellanslag innan kolumn
-   Åsidosätt format/valuta
-   Utskriftskontroll

### <a name="changing-the-column-width"></a>Ändra kolumnbredden

Cellen **Kolumnbredd** anger antalet tecken som ska användas för bredden på den här kolumnen på den utskrivna rapporten. Kolumnbredden är viktig för kolumner som innehåller belopp (kolumner av typen **CALC**, **WKS**, eller **FD**), beskrivningar (kolumner av typen **DESC**), eller fyll (kolumner av typen **FILL**). Som standard väljs alternativet **Autoanpassning** så att bredden för varje kolumn justeras automatiskt för att passa innehållet.

#### <a name="specify-the-width-of-a-column-on-a-report"></a>Ange bredden för en kolumn i en rapport

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  I cellen **Kolumnbredd** anger du antal blanksteg för kolumnens bredd. Den maximala bredden på en kolumn är 255 tecken (detta nummer inkluderar SEK, kommatecken och parenteser). Alternativt kan du dubbelklicka på cellen **Kolumnbredd** och sedan på **Autoanpassning** om du vill möjliggöra för rapportutformaren att välja lämplig bredd för kolumnen baserat på cellinnehållet.

### <a name="add-space-between-columns"></a>Lägg till blanksteg mellan kolumner

Cellen **Ytterligare blanksteg innan kolumn** anger bredden på avgränsaren mellan en kolumn och intilliggande kolumner i kolumndefinitionen. Inställningen **Ytterligare blanksteg innan kolumn** påverkar alla kolumndetaljrader för kolumnen, men inte kolumnrubrikraderna. Använd det här alternativet om du vill avgränsa kolumner eller lägga till några blanksteg före beskrivningen så att beskrivningskolumnen dras in från de vänsterjusterade rubrikerna i rapporten. Standardantalet blanksteg mellan varje kolumn är två. Du kan ändra den här inställningen på fliken **Inställningar** i rapportdefinitionen.

#### <a name="specify-the-space-between-columns"></a>Ange blanksteg mellan kolumner

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  I cellen **Ytterligare blanksteg innan kolumn** anger du det antal blanksteg som ska infogas mellan kolumner.

### <a name="specify-a-currency"></a>Ange en valuta

Cellen **Åsidosätt format/valuta** anger formateringen av decimaltecken-, valuta- och procentsatsbeloppen i kolumnen. Denna formatering åsidosätter den eventuella formatering som anges i rapportdefinitionen eller systemets standardinställningar.

#### <a name="assign-a-format-currency-override-to-a-report-column"></a>Tilldela en åsidosättning av format eller valuta till en rapportkolumn

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på cellen **Åsidosätt format/valuta** i en beloppskolumn.
3.  Välj formateringsalternativ i dialogrutan **Formatåsidosätt**.

### <a name="add-a-print-control-code"></a>Lägg till en utskriftskontrollkod

Cellen **Utskriftskontroll** kan innehålla koder som justerar visningen eller utskriften av egenskaperna för en kolumn. Det finns två typer av utskriftskontrollkoder: vanliga utskriftskontrollkoder och villkorsstyrda utskriftskontrollkoder.

#### <a name="regular-print-control-codes"></a>Vanliga utskriftskontrollkoder

| Skriv ut utskriftskontrollkod | Översättning                                     | Beskrivning                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|--------------------|-------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NP                 | Icke utskriftsbara                                     | Exkludera beloppen i denna kolumn från rapporten som skrivs ut och från beräkningar. Mer information finns i kolumnen direkt i beräkningsformeln om du vill inkludera icke utskriftsbara kolumner i beräkningen. Exempelvis inkluderas den icke utskriftsbara kolumnen C i följande formel: **B+C+D**. Exempelvis inkluderas den icke utskriftsbara kolumnen C inte i följande formel: **B:D**.                                                                                                                                          |
| XCR                | Ändra tecknet om vanligt saldo på raden är kredit | Skapa en budget eller jämförande rapport där eventuella ofördelaktiga avvikelser (till exempel intäktbrist eller utgiftsöverskridning) alltid är negativ. Tillämpa den här koden till en **CALC**-kolumn om du vill återställa tecknet för kolumnbeloppet, om det vanliga saldot för en viss rad är en kredit (som identifieras av ett **C** i kolumnen **Normalt saldo** i raddefinitionen.) **Obs!** För **TOT**-rader och **CAL**-rader som vanligtvis har ett kreditsaldo ska du se till att ange ett **C** i kolumnen **Normalt saldo** i raddefinitionen. |
| X0                 | Undertryck kolumnen om alla är noll eller tomma          | Exkludera en **FD**-kolumn från rapporten om alla celler i den kolumnen är antingen tomma eller innehåller nollor.                                                                                                                                                                                                                                                                                                                                                                                                                             |
| SR                 | Undertryck avrundning                               | Förhindra beloppen i denna kolumn från att avrundas.                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| XR                 | Undertryck ackumulerade                                 | Undertryck ackumulerade. Om rapporten använder ett rapportträd, är beloppen i denna kolumn inte ackumulerade till överordnade noder.                                                                                                                                                                                                                                                                                                                                                                                                   |
| RP                 | Upprepa kolumnen på varje sida                      | Upprepa en viss kolumn på varje sida i en rapport. Du kan till exempel använda utskriftskontrollen **RP** om du vill inkludera en kolumn med typen **ROW** som drar in radkoder på varje sida.                                                                                                                                                                                                                                                                                                                                           |
| WT                 |  Radbryt text                                      |  Om texten i en kolumn är för lång för att passa utrymmet, radbryter du texten för att hålla all text i kolumnen.                                                                                                                                                                                                                                                                                                                                                                                                                            |

#### <a name="conditional-print-control-codes"></a>Villkorsstyrda utskriftskontrollkoder

| Villkorsstyrd utskriftskontrollkod | beskrivning                                                                             |
|--------------------------------|-----------------------------------------------------------------------------------------|
| (ingen)                         | Rensa det villkorsstyrda utskriftsvalet.                                                  |
| P&lt;B                         | Visa bara en specifik kolumn om perioden är mindre än basperioden.             |
| P&gt;B                         | Visa bara en specifik kolumn om perioden är mer än basperioden.             |
| P=B                            | Visa bara en specifik kolumn om perioden är lika med basperioden.              |
| P&lt;=B                        | Visa bara en specifik kolumn om perioden är mindre än eller lika med basperioden. |
| P&gt;=B                        | Visa bara en specifik kolumn om perioden är mer än eller lika med basperioden. |

#### <a name="add-print-control-codes-to-a-report-column"></a>Lägg till utskriftskontrollkoder till en rapportkolumn

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på cellen **Utskriftskontroll**.
3.  I dialogrutan **Utskriftskontroll** väljer du en kod i listan **Välj alternativ för utskriftskontroll** . Håll ned CTRL-tangenten medan du väljer koderna om du vill välja mer än en kod.
4.  Välj ett alternativ i fältet **Villkorsstyrda utskriftsalternativ**. **(ingen)** är markerad som standard. Du kan bara välja en villkorsstyrd utskriftskod åt gången
5.  Klicka på **OK**.

> [!TIP]
> Du kan också skriva utskriftskontrollkoder direkt i cellen **Utskriftskontroll**. Separera flera utskriftskontrollkoder med kommatecken.


## <a name="column-types"></a>Kolumntyper
Typen av information som varje kolumn i en rapport innehåller, anges av värdet i raden **Kolumntyp** i kolumndefinitionen. Varje kolumndefinition måste innehålla minst en beskrivningskolumn (**DESC**) och en beloppskolumn (,**FD**, **WKS**eller **CALC**. **Obs!** Kolumntypkoderna gäller inte för alla redovisningssystem. Om du väljer en typ som är inte giltig för ditt redovisningssystem, är den kolumnen tom i rapporten.

### <a name="specify-a-column-type"></a>Ange en kolumntyp

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på en cell i raden **Kolumntyp** i lämplig kolumn.
3.  Välj en kolumntyp i listan. Följande tabell beskriver olika kolumntyper.
    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Kolumntypkod</th>
    <th>Beskrivning</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>FD</td>
    <td>Visa ekonomiska data eller data från ett Excel-kalkylblad när du använder kolumnen <strong>Länk till ekonomiska dimensioner</strong> eler kolumnen <strong>Länk till kalkylblad</strong> i raddefinitionen. När du väljer kolumntypen <strong>FD</strong> anges standardinställningen automatiskt för följande rader: <ul>
    <li><strong>Bokkod/attributkategori:</strong> ACTUAL</li>
    <li><strong>Bokkod/attributkategori:</strong> ACTUAL</li>
    <li><strong>Räkenskapsår:</strong> BASE</li>
    <li><strong>Period:</strong> BASE</li>
    <li><strong>Täckta perioder:</strong> PERIODIC</li>
    <li><strong>Kolumnbredd:</strong> 14</li>
    </ul>
Du kan ändra dessa standardinställningar.</td>
    </tr>
    <tr class="even">
    <td>CALC</td>
    <td>Visa resultatet av en enskild eller komplicerad beräkning som anges i cellen <strong>Formel</strong>. Mer information finns i <a href="advanced-formatting-options-financial-reporting.md">Avancerade formateringsalternativ i ekonomiska rapporter</a>.</td>
    </tr>
    <tr class="odd">
    <td>DESC</td>
    <td>Visa radbeskrivningen från raddefinitionen. Även om beskrivningskolumnen ofta är den första kolumnen i rapporten, kan den placeras var som helst.</td>
    </tr>
    <tr class="even">
    <td>ROW</td>
    <td>Visa de enskilda radkoderna för ekonomiska rader från kolumnen <strong>Radkod</strong> i raddefinitionen. Mer information finns i <a href="row-definitions-financial-reporting.md">Raddefinitioner i ekonomiska rapporter</a>.</td>
    </tr>
    <tr class="odd">
    <td>ACCT (kontokoder)</td>
    <td>Visa de ekonomiska datasegmentvärden eller dimensionsvärden som gäller för varje rad. För konto- och transaktiondetaljrapporter skrivs det helt kvalificerade kontot ut (t.ex. <strong>110140-070-0101</strong>). Om intervall har angetts i kolumnen <strong>Länk till ekonomiska dimensioner</strong> i en associerad raddefinition omges intervallet av hakparentes och behandlas som ett enskilt värde (t.ex. <strong>[110140:110700]-070-[0101:0200]</strong>). För ekonomiska rapporter och rapporter på hög nivå som är en kombination av flera konton, skrivs den ekonomiska datalänken ut från raddefinitionen (t.ex. <strong>1100:1200</strong>).</td>
    </tr>
    <tr class="even">
    <td>FILL</td>
    <td>Fyll cellen med ett tecken som du omger med enkla citationstecken. Om du inte anger ett tecken, är kolumnen tom. För att fylla en kolumn med en ellips (...) anger du till exempel <strong>FILL</strong> <strong>"."</strong>.</td>
    </tr>
    <tr class="odd">
    <td>SIDA</td>
    <td>Infoga en lodrät sidbrytning i rapporten. Kolumnerna som är till höger om <strong>PAGE</strong> visas på olika sidor.</td>
    </tr>
    <tr class="even">
    <td>WKS</td>
    <td>Visa data som hämtas från ett Excel-kalkylblad. När du väljer kolumntypen <strong>WKS</strong> anges standardinställningen automatiskt för följande rader: <ul>
    <li><strong>Räkenskapsår:</strong> PERIODIC</li>
    <li><strong>Period:</strong> BASE</li>
    </ul>
Du kan ändra dessa standardinställningar.</td>
    </tr>
    <tr class="odd">
    <td>ATTR</td>
    <td>Om ditt redovisningssystem stöder attribut visas ett konto- eller transaktionsattribut i kolumnen. Ett attribut som ska användas för ett enkelt fulständigt konto, hämtar underliggande konto eller transaktionsinformation från ekonomiska data. Attributen på kontonivå visar data från kontot, och attributen på transaktionsnivå visar data som uppstått vid den tidpunkt då transaktionen bokfördes. Om du väljer <strong>ATTR</strong> som kolumntyp, ange då attributkategorin i detaljraden <strong>Redovisningskod/Attributkategori</strong> för kolumndefinitionen.</td>
    </tr>
    </tbody>
    </table>

### <a name="financial-dimensions-column"></a>Kolumnen Ekonomiska dimensioner

Följande raddefinitioner för **Kolumndefinition** gäller för kolumner som har kolumntypen **FD** (belopp från ekonomiska dimensioner).

#### <a name="book-codeattribute-category-cell"></a>Cellen bokkod/attributkategori

Cellen **Bokkod/attributkategori** identifierar bokkoden för data i kolumnen **FD**. En kolumndefinition kan innehålla flera aktuella, budget- och statistiska kolumner. En kolumndefinition kan också visa olika perioder, till exempel aktuell eller hittills i år och olika belopp. Listan med bokkoder återspeglar den alternativen aktuell, budget och statistisk (inte ekonomisk) som har skapats i dina ekonomiska data.

#### <a name="fiscal-year-cell"></a>Cellen Räkenskapsår

Cellen **Räkenskapsår** identifierar det räkenskapsår som kolumnen ska inkludera. Året kan vara relativt till basåret som anges när rapporten genereras. Följande alternativ är tillgängliga.

| Alternativ  | Beskrivning                                                                                                                  |
|---------|------------------------------------------------------------------------------------------------------------------------------|
| BASE    | Använd basåret som anges på rapporttid.                                                                          |
| BASE+\# | Använd året som är \# år efter basåret. Om du till exempel vill använda det tredje året efter basåret, anger du **BASE+3**. |
| BASE-\# | Använd året som är \# år före basåret. Om du till exempel vill använda föregående år, ange **BASE-1**.                 |
| \#      | Ange det faktiska räkenskapsåret.                                                                                                |

#### <a name="period-cell"></a>Periodcell

Cellen **Period** identifierar de räkenskapperioder som kolumnen ska inkludera. Perioden kan vara relativ i förhållande till basperioden som har angetts när rapporten genereras. Följande alternativ är tillgängliga.

| Alternativ          | beskrivning                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BASE            | Använd basperioden.                                                                                                                                                                                                                 |
| BASE+\#         | Använd perioden som är \# perioder efter basperioden.. Om du till exempel vill använda den tredje perioden efter basperioden anger du **BASE+3**.                                                                                               |
| BASE-\#         | Använd perioden som är \# perioder före basperioden. Om du till exempel vill använda föregående period, ange **BASE-1**.                                                                                                                 |
| BASE-\#:BASE    | Använd flera perioder, från flera perioder före basperioden genom basperioden. Om du till exempel vill använda de tre föregående perioderna och basperioden, anger du **BASE-3:BASE**                                                |
| BASE:BASE+\#    | Använd flera perioder, från basperioden genom flera perioder efter basperioden. Om du till exempel vill använda basperioden och de tre följande perioderna, anger du **BASE:BASE+2**                                                  |
| BASE-\#:BASE+\# | Använd flera perioder, från flera perioder före basperioden till flera perioder efter basperioden. Om du till exempel vill använda de tre föregående perioderna, basperioden och följande två perioder, anger du **BASE-3:BASE+2** |
| 1:BASE          | Använd flera perioder, från den första perioden genom basperioden.                                                                                                                                                                 |
| \#              | Använd alltid ett specifikt periodnummer. Vi rekommenderar att du inte använder det här alternativet eftersom det minskar kolumndefinitionens flexibilitet.                                                                                       |
| \#                                      : \#           | Använd alltid ett specifikt periodintervall. Vi rekommenderar att du inte använder det här alternativet eftersom det minskar kolumndefinitionens flexibilitet.                                                                                    |

Du kan gå bakom räkenskapsårets begränsningar i någon av periodspecifikationerna, och du kan blanda år i ett periodintervall. Till exempel anger du perioderna som **BASE-5** (som föregående sex perioder) och kör en rapport med basperiod 2. I det här fallet visar rapporten data för de första två perioderna under angivet räkenskapsår och de sista fyra perioderna under föregående räkenskapsår.

### <a name="specify-the-periods-for-an-fd-column"></a>Ange perioderna för en FD-kolumn

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  I en **FD**-kolumn, dubbelklicka på raden och välj **Period** och välj sedan ett alternativ i listan.
3.  Fyll i formeln i formelfältet ovanför navigeringsfönstret eller i cellen **Period**. Byt ut valfritt nummertecken (\#) mot lämpligt värde.

#### <a name="periods-covered-cell"></a>Cellen Täckta perioder

Cellen **Täckta period** identifierar de belopp som kolumnen ska visa. Detta belopp är relativt till värdet i cellerna **Räkenskapsår** och **Period** för kolumnen. Följande alternativ är tillgängliga.

| Alternativ      | Beskrivning                                                                 |
|-------------|-----------------------------------------------------------------------------|
| PERIODISK    | Visa summan av aktiviteten för den aktuella perioden eller periodintervallet. |
| PERIODIC/BB | Visa det ingående saldot för den aktuella perioden eller periodintervallet.   |
| YTD         | Visa summan för aktiviteten hittills i år.                               |
| YTD/BB      | Visa årets ingående saldo.                                 |

### <a name="specify-the-periods-that-are-covered-for-an-fd-column"></a>Ange perioderna som täcks av en FD-kolumn

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  I en **FD**-kolumn, dubbelklicka på raden och välj **Täckta perioder** och välj sedan ett alternativ i listan.

### <a name="attribute-filter-in-a-column-definition"></a>Attributfilter i en kolumndefinition

Attribut är ekonomiska datavärden som ytterligare definierar ett konto eller en transaktion. Kontoattributen inkluderar **Tillgång**, **Skuld**, **Intäkt** och **Utgift**. Transaktionattributen inkluderar **Transaktionbeskrivning** och **Transaktionens tillämpningsdatum**. Attributsupport kan skilja sig mellan Microsoft Dynamics ERP-system. Cellen **Attributfilter** begränsar data i **FD**-kolumner till specifika värden eller intervall för attributkategorier. Även om den här funktionen kan användas tillsammans med en **ATTR**-kolumn krävs inte **ATTR**-kolumnen. I **FD**-kolumnen finns det en gräns för de konton eller transaktioner som rapporten ska inkludera i attributfiltret. **Obs!** Mer information om vilka attribut som dina ERP-system ger stöd för finns i systemets integrationshandbok.

#### <a name="apply-an-attribute-filter-for-an-fd-column-on-a-report"></a>Tillämpa ett attributfilter för en FD-kolumn i en rapport

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på cellen **Attributfilter** för en **FD**-kolumn.
3.  I dialogrutan **Attributfilter**, dubbelklicka på en cell i kolumnen och välj sedan kolumnen **Attribut** och välj sedan filtertypen.
4.  Ange ett intervall i kolumnerna **Från** och **Till** för att ytterligare begränsa resultaten. Cellen **Från** måste innehålla ett värde.
5.  Klicka på **OK**.

#### <a name="example-of-an-attribute-filter"></a>Exempel på ett attributfilter

Följande exempel visar en del av en kolumnbeskrivning som har ett kontoattribut i raden **Bokkod/attributkategori**. Attributfiltret för den här kolumnen anger intervallet av värden som ska inkluderas i rapporten.

|                              | A    | G                    |
|------------------------------|------|----------------------|
| Kolumntyp                  | DESC | FD                   |
| Bokkod/attributkategori |      | AKTUELL               |
| Räkenskapsår                  |      | BASE                 |
| Period                       |      | 1:BASE               |
| Täckta perioder              |      | PERIODISK             |
| ...                          |      |                      |
| Kolumnbredd                 | 30   |                      |
| ...                          |      |                      |
| Attributfilter             |      |  Referens=\[01:10\] |

### <a name="dimension-filter-in-a-column-definition"></a>Dimensionsfilter i en kolumndefinition

Ett dimensionsfilter används för att begränsa **FD**-kolumnen till specifika dimensionsvärden. Filtret kan innehålla en enda dimension, ett intervall av dimensioner eller en grupp av dimensioner. Filtret kan också inkludera dimensionsvärdeuppsättningar. Eftersom dimensionsvärden kan variera, måste ett inte ...\ekonomiska-dimensioner\dimensionsbaserat system stämma överens med en exakt längd. Filtret används oavsett om rapporten omfattar ett rapportträd. Du kan använda ett jokertecken (\* eller ?) på valfri position. När du anger flera konton kan du sätta ett kommatecken mellan kontona som i följande exempel: +Konto=\[1200\], +Konto=\[1100\], Avdelning=\[01?\] Om du vill ta emot alla avdelningar för ett visst konto kan du utelämna avdelningsdimensionen från dimensionfiltret. Om till exempel båda av följande dimensionfilter hanteras på samma sätt:

-   +Konto=\[1100\],Avdelning
-   +Konto=\[1100\]

Du kan också använda någon kombination av alfanumeriska tecken för exakt matchning och du kan definiera deldimensioner. Exempelvis inkluderar **Plats = \[10\*\]** alla värden för platsdimensioner som börjar på 10.

#### <a name="apply-a-dimension-filter-for-a-column-on-a-report"></a>Tillämpa en filterdimension för en kolumn i en rapport

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på cellen **Dimensionsfilter** för en **FD**-kolumn.
3.  I dialogrutan **Dimensioner** anger du vilka filter som ska användas.
4.  Klicka på **OK**.

### <a name="format-a-multiple-currency-report-in-a-column-definition"></a>Formatera en rapport med flera valutor i en kolumndefinition

En rapport med flera valutor kan visa belopp i den naturliga valutan (lokal valuta), funktionella valutan (standardinställning) eller rapporteringsvalutan. Ett företags funktionella valuta definieras i ERP-systemet i Microsoft Dynamics. Förväxla inte den här ERP-inställningen med operativsystemets regionala alternativinställningar där du kan ange de symboler för standardinställd valuta som används i rapporter. Följande valutarelaterade celler är tillgängliga i kolumndefinitionen:

-   **Valutavisning** – Ange valuta (naturlig, funktionell eller rapportering) som visas i transaktionerna. Den här funktionen kallas ibland för valutaomräkning. Valutaomräkning är förmågan att rapportera redovisningsbelopp i en valuta som inte kanske är företagets funktionella valuta eller den valuta som transaktionen angavs i.
-   **Valutafilter** – Ange ett valutafilter. Endast transaktioner som anges i den valda valutan visas i rapporten.

> [!NOTE]
> Om du vill skapa rapporter som använder flera valutor måste du markera kryssrutan **Inkludera alla rapporteringsvalutor** på fliken **Rapport** i rapportdefinitionen. Följ stegen nedan om du vill avgöra ett företags funktionella valuta.

1.  I Report Designer, på menyn **Företag** klickar du på **Företag**.
2.  I dialogrutan **Företag** väljer du ett företag och klickar sedan på **Visa**.
3.  I dialogrutan **Visa information om företag** under **Regionala alternativ**, kan du visa den valuta som definierats för det valda företaget.

#### <a name="specify-the-currency-on-a-multiple-currency-report"></a>Ange valutan på en rapport med flera valutor

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  Dubbelklicka på cellen **Valutabildskärm** i rätt **FD**-kolumn och välj sedan alternativet för att visa valutainformation: **Naturlig/ursprunglig valuta**, **Funktionell valuta från företagsinformation**eller rapporteringsvalutan.
3.  Dubbelklicka på cellen **Valutafilter** i rätt **FD**-kolumn och välj rätt valutakod i listan. Endast transaktioner som anges i denna valutan visas i rapporten.

> [!NOTE]
> Alternativen som beskrivs här kan komma att skilja sig beroende på ERP-systemet. Mer information finns i [systemdokumentationen för Microsoft ERP](https://www.microsoft.com/en-us/download/details.aspx?id=5916).

### <a name="example-for-currency-display-and-currency-filter-cells"></a>Exempel på celler för Valutavisning och Valutafilter

Phyllis har gjort följande valutaval i sin kolumndefinition:

-   **Valutafilter:** Yen
-   **Valutabildskärm:** Funktionell (USD)

På grund av valutafiltret som Phyllis markerat, innehåller rapporten endast transaktioner som registreras i japanska yen (JPY). På grund av valutabildskärmen som hon har markerat, visar rapporten de transaktionerna i den funktionella valutan USD,

#### <a name="currency-filter-and-currency-display-combinations"></a>Kombinationer av Valutafilter och Valutavisning

Följande tabell visar rapportresultaten som kan uppstå för olika kombinationer av alternativen i **Valutavisning** och **Valutafilter** på grund av valen som Phyllis har gjort. Den funktionella valutan är USD.

| Cellen Valutavisning                        | Cellen Valutafilter | Rapportresutat                                                                                                                                                                                    |
|----------------------------------------------|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Naturligt/ursprunglig valuta                 | **YEN**              | **6 000 Y** – Resultatet visas endast transaktioner som angavs i JPY.                                                                                                                        |
| Funktionell valuta från företagsinformation | **YEN**              | **60 $** – Resultatet visar endast transaktioner som angavs i JPY, och visar de transaktionerna i USD. **Obs!** konverteringskursen är ungefär 100 JPY per USD.                    |
| Funktionell valuta från företagsinformation | Tom                | **$2,310\*\*** – Resultatet visar alla data i den funktionella valutan som anges i företagsinformationen. **Obs!** Detta belopp är summan av alla transaktioner i funktionell valuta. |
| Naturlig/ursprunglig valuta                 | Tom                | **2 250 $** - Resultatet visar alla belopp i den valuta som transaktionen genomfördes i.                                                                                                 |

### <a name="calculation-column-in-a-column-definition"></a>Beräkningskolumn i en kolumndefinition

Kolumntypen **BERÄKNA** i en kolumndefinition stöder komplexa beräkningar i cellen **Formel** och kan innehålla operatorerna **+**, **-**, **\*** och **/**, samt **OM/SÅ/ANNAT**-utdrag. En beräkningskolumn kan också referera till valfri kolumn och även efterföljande kolumner. Dessutom kan en beräkningskolumn även inkludera perioden och räkenskapsåret för att stödja rubriker för kolumnen. Beräkningsformeln kan vara upp till 1,024 alfanumeriska tecken. Använd en särskild formatåsidosättning för att uttrycka beräkningsresultatet i procent. **Obs!** Resultatet av beräkningsformler inkluderar inte värdena i icke utskriftsbara kolumnintervall. Till exempel **A:D** skriver ut **0** (noll), medan **A+B+C** för icke utskriftsbara värden beräknar värdet.

#### <a name="operators-in-calculation-columns"></a>Operatorer i beräkningskolumner

Ange kolumnbokstäverna i uträkningsordningen och använd sedan en operator som separerar varje kolumnbokstav om du vill addera, subtrahera, multiplicera eller dividera kolumner. Följande register innehåller information om operatörerna som du kan använda i en beräkningskolumn.

| Operatör | Beräkningsexempel | beskrivning                                                                                                                                                                                                                                    |
|----------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| +        | A+C                 | Lägg till beloppet i Kolumn A till beloppet i Kolumn C.                                                                                                                                                                                          |
| :        | A:C A:C-D           | Lägg till ett intervall med på varandra följande kolumner. Till exempel formeln **A:C** adderar summorna av kolumner A till C, och formeln **A:C-D** adderar summorna av kolumner A till C och subtraherar sedan beloppet i kolumn D.                          |
| -        | A-C                 | Subtrahera beloppet i kolumn A från beloppet i kolumn C. **Obs!** Du kan också använda minustecknet (-) om du vill återföra tecknen i en kolumn. Använd t.ex. **-A+B** om du vill addera det omvända av beloppet i kolumn A till beloppet i kolumn B. |
| \*       | A\*C                | Multilicera beloppet i kolumn A med beloppet i kolumn C.                                                                                                                                                                                     |
| /        | A/C                 | Dividera beloppet i kolumn A med beloppet i kolumn C.                                                                                                                                                                                       |

#### <a name="use-a-calculation-formula-in-a-column-definition"></a>Använd en beräkningsformel i en kolumndefinition

1.  Öppna kolumndefinitionen för att ändra den i Report Designer.
2.  I lämplig **CALC**-kolumn anger du en formel i cellen **Formel** .

#### <a name="complex-calculations"></a>Komplexa beräkningar

En komplexa beräkning kan innehålla en valfri kombination av cellreferenser, operatorer, värden och nivåer för kapslade parenteser. Använd t.ex. beräkningsformeln **((A+B)/2)** för att beräkna medelvärdet för kolumner A och B.

#### <a name="specify-report-cells-in-a-column-calculation"></a>Ange rapportceller i en kolumnberäkning

Du kan referera till en viss rapportcell, genom att ange en kolumnbokstav och en radkod. T.ex. refererar **B.100** till radkod 100 i kolumn B. Du kan dela en hel kolumn med ett visst rapportcellbelopp som finns i samma kolumn. Till exempel betyder beräkningen **B/B.100** att beloppet i kolumn B ska delas av värdet i radkod 100 i kolumn B. Om beräkningen refererar till en kolumn som är beroende av en annan kolumn, löses den beroende kolumnen först. Om du refererar en kolumn i en annan kolumn som refererar tillbaka till den första kolumnen kommer du att göra ett cirkulärt referensfel. **Obs!** Beräkningen kan bli fel om du ändrar beräkningsprioriteten för rapporten. Du kan ange beräkningsprioriteten på fliken **Inställningar** av rapportdefinitionen.

#### <a name="multiply-or-divide-a-column-by-a-base-row"></a>Multiplicera eller dela upp en kolumn med basrad

Du kan skapa en kolumn som visar alla värden i en viss kolumn som en procentandel av ett basnummer. Därför kan du visa relationer mellan rader som till exempel en procentandel av en försäljningrad eller en procentandel av en rad för totala utgifter. Om du vill multiplicera eller dela upp varje rad i en viss kolumn med en basrad, ange en kolumn som ska användas i beräkningen och ange sedan **\*BASEROW** eller **/BASEROW**. Ange till exempel **C\*BASEROW** or **C/BASEROW**. **Obs!** Kontrollera att varje raddefinition som används med denna kolumndefinition när du använder en basradberäkning i en kolumndefinition, innehåller minst en basrad för beräkningar.

#### <a name="divide-the-amount-in-a-column-by-the-number-of-periods"></a>Dela beloppet i en kolumn med antalet perioder

Du kan dela beloppet i en kolumn med ett specifik antalet perioder. Till exempel delar formeln **B/Periods** värdet i kolumn B med antalet perioder i kolumn B. Om beräkningen omfattar flera kolumner, anger du antalet perioder som ska användas i beräkningen. Om du till exempel adderar formeln **(B+C)/Periods** beloppen i kolumn B och C kolumn och sedan delar resultatet med periodvärdet.

<a name="see-also"></a>Se även
--------

[Rapportdefinitioner i ekonomiska rapporter](row-definitions-financial-reporting.md)

[Avancerade formateringsalternativ i ekonomiska rapporter](advanced-formatting-options-financial-reporting.md)




