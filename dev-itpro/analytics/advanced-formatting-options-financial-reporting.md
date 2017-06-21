---
title: Avancerade formateringsalternativ i ekonomiska rapporter
description: "När du skapar en rapport inom ekonomisk rapportering blir ytterligare formateringsfunktioner tillgängliga, inklusive filter för dimensioner, begränsningar för kolumner och rapportenheter, icke-utskriftsrader samt IF/THEN/ELSE-utdrag i beräkningar."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter
ms.custom: 106571
ms.assetid: 895b5127-01d6-4495-b127-343387b743aa
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: cc22e564c68ab04c61f2a2fc9d0a70335dc05b06
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="advanced-formatting-options-in-financial-reporting"></a>Avancerade formateringsalternativ i ekonomiska rapporter

[!include[banner](../includes/banner.md)]


När du skapar en rapport inom ekonomisk rapportering blir ytterligare formateringsfunktioner tillgängliga, inklusive filter för dimensioner, begränsningar för kolumner och rapportenheter, icke-utskriftsrader samt IF/THEN/ELSE-utdrag i beräkningar. 

I följande tabell beskrivs de avancerade formateringfunktionerna som är tillgängliga när du utformar rapporter.

| Funktion                   | Beskrivning                                                                                                                                                                                                                                                                                                                     |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dimensionsfilter           | Om du vill ha åtkomst till specifika datauppsättningar kan du använda dimensioner i raddefinitionen och kolumndefinitionen. Många rapporter använder bara radformatets naturliga segment. Du kan dock ändra rader, så att de omfattar dimensionsvärden. Dimensionsfilter i kolumndefinitionen används för att f¨åtkomst till specifika dimensionsvärden. |
| Rapportenhetsbegränsning | Du kan ställa in en rapportrad, så att den bara visar information som är kopplad till en viss rapportenhet.                                                                                                                                                                                                                      |
| Icke utskriftsbara rader (NP)     | Icke utskriftsbara rader är användbara för många rapporter. Om flera beräkningar krävs för att skapa ett värde, kan dessa beräkningar döljas på den utskrivna rapporten. Icke utskriftsbara rader är också bra för felsökning i rapportdesigner och för avancerad cellplacering.                                                    |
| Kolumnbegränsning         | Kolumnbegränsningen i raddefinitionen är användbar när du vill dölja relevanta värden bara på några rader i rapporten. När procentsatsberäkningar utförs på en rad, förhindrar kolumnbegränsningen totala kolumner eller andra kolumner från att skrivas ut när dessa nummer inte gäller.                              |
| Kolumnavbrott               | Du kan lägga till kolumnavbrott i en raddefinition för att visa rapportinformation parallellt. Du kan lägga till flera kolumnavbrott i en enda raddefinition och kolumnrubriker upprepas högst upp i varje kolumn efter kolumnavbrott. Kommentarer för en rapport visas mellan kolumnavbrotten.                              |
| IF/THEN/ELSE-utdrag     | Du kan ändra definitionen för beräkningar i följd eller en kolumndefinition.                                                                                                                                                                                                                                                         |

## <a name="advanced-cell-placement"></a>Avancerad cellplacering
Den avancerade cellplaceringen eller *framtvinga*placeringen av specifika värden till specifika celler. Exempelvis används ofta framtvinga till att flytta det korrekta saldot i ett kassaflödesutdrag. Du kan använda framtvinga i följande syften:

-   Flytta värden från Microsoft Excel till specifika celler.
-   Hårdkodat specifika detaljvärden till en rapport.
-   Ändra tecken genom att kopiera ett värde från en tidigare cell och att multiplicera det värdet med -1.

**Obs!** I många fall måste du konfigurera din rapportdefinition, så att kolumnberäkningar görs före radberäkningar. Om du vill slutföra den här konfigurationen.

1.  I Report Designer öppnar du rapportdefinitionen.
2.  På fliken **Inställningar** under **Beräkningsprioritet**är **Utför kolumnberäkningen först och sedan rad**.

## <a name="designing-the-report"></a>Designa rapporten
Om du utformar en rapport ska du först skapa alla detaljrader för att säkerställa att värdena dras in som förväntat. Lägg sedan till **NP** (ingen utskrift) formatåsidosätt för att dölja information som innehåller de senaste värdena. **Viktigt:** När du använder formatkoden **CAL** i raddefinitionen kan du inte gå ner till transaktiondetaljen. För framtvingande använder formler följande format: &lt;destinationskolumn&gt;=&lt;ursprunglig kolumn&gt;.&lt;radkod&gt; Separera alla ytterligare placeringar för en rad med komma och mellanslag. Här finns ett exempel: D=C.190 E=C.100

## <a name="examples-of-advanced-formatting-options"></a>Exempel på avancerade formateringsalternativ
Följande exempel visar hur du öppnar raddefinitionen och kolumndefinition om du vill aktivera en grundläggande kassaflödesrapport (exempel 1) och en statistisk rapport (exempel 2) .

### <a name="example-1-basic-forcing"></a>Exempel 1: Grundläggande framtvinga

Följande tabell visar ett exempel på en raddefinition som använder grundläggande framtvingning.

| Radkod | Beskrivning                      | Formatkod | Relaterade formler/rader/enheter | Formatåsidosätt | Normalbalans | Utskriftskontroll | Kolumnbegränsning | Radmodifierare               | Länk till ekonomiska dimensioner |
|----------|----------------------------------|-------------|-----------------------------|-----------------|----------------|---------------|--------------------|----------------------------|------------------------------|
| 100      | Likvida medel vid periodens början (NP) |             |                             |                 |                |               |                    | Kontomodifierare = \[/BB\] | +Segment 2 = \[1100\]         |
| 130      | Likvida medel vid periodens början      | CAL         | C=C.100 F=D.100             |                 |                |               |                    |                            |                              |
| 160      |                                  |             |                             |                 |                |               |                    |                            |                              |
| 190      |                                  |             |                             |                 |                |               |                    |                            |                              |

Följande tabell visar ett exempel på en kolumndefinition som använder grundläggande framtvingning i raden.

|                              | A   | G    | C        | D      | E      | F    |
|------------------------------|-----|------|----------|--------|--------|------|
| Rubrik 1                     |     |      |          |        |        |      |
| Rubrik 2                     | A   | G    | C        | D      | E      | F    |
| Rubrik 3                     |     |      |          |        |        |      |
| Kolumntyp                  | ROW | DESC | FD       | FD     | FD     | CALC |
| Bokkod/attributkategori |     |      | AKTUELL   | AKTUELL | AKTUELL |      |
| Räkenskapsår                  |     |      | BAS     | BAS   | BAS   |      |
| Period                       |     |      | BAS     | BAS   | BAS   |      |
| Täckta perioder              |     |      | PERIODISK | YTD/BB | YTD    |      |
| Formel                      |     |      |          |        |        | E-D  |
| Kolumnbredd                 | 5   | 30   | 14       | 14     | 14     | 14   |

### <a name="example-2-statistical-reports"></a>Exempel 2: Statistiska rapporter

Följande tabell visar ett exempel på en raddefinition som använder framtvingning för en statistisk rapport.

| Radkod | Beskrivning               | Formatkod | Relaterade formler/rader/enheter     | Formatåsidosätt      | Normalbalans | Utskriftskontroll | Kolumnbegränsning | Radmodifierare | Länk till ekonomiska dimensioner               |
|----------|---------------------------|-------------|---------------------------------|----------------------|----------------|---------------|--------------------|--------------|--------------------------------------------|
| 50       | Statistisk information   | REM         |                                 |                      |                |               |                    |              |                                            |
| 100      | Personalstyrka - USA            | CAL         | 4                               | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 115      | Personalstyrka - Internationell | CAL         | 11                              | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 130      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 190      | USA-försäljningar                  |             |                                 |                      | C              |               |                    |              | +Segment 2 = \[41\*\], Segment 3 = \[00\]    |
| 220      | Internationell försäljning       |             |                                 |                      | C              |               |                    |              | +Segment 2 = \[41\*\], Segment 3 = \[01:99\] |
| 250      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 280      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 310      | USA-försäljningar                  | CAL         | D=C.190,E=C.100,F=(C.100/C.190) |                      |                |               |                    |              |                                            |
| 340      | Internationell försäljning       | CAL         | D=C.220,E=C115,F=(C.220/C.115)  |                      |                |               |                    |              |                                            |

Följande tabell visar ett exempel på en radkolumn som använder framtvingning för en statistisk rapport.

|                              | A   | B    | C      | D            | E     | F            |
|------------------------------|-----|------|--------|--------------|-------|--------------|
| Rubrik 1                     | A   | B    | C      | D            | E     | F            |
| Rubrik 2                     | -   | -    | YTD (innevarande år fram till dags dato)    | Årlig försäljning | Personal | SEK per person |
| Rubrik 3                     |     |      |        |              |       |              |
| Kolumntyp                  | ROW | DESC | FD     | CALC         | CALC  | CALC         |
| Bokkod/attributkategori |     |      | AKTUELL |              |       |              |
| Räkenskapsår                  |     |      | BAS   |              |       |              |
| Period                       |     |      | BAS   |              |       |              |
| Täckta perioder              |     |      | YTD    |              |       |              |
| Formel                      |     |      |        |              |       | E-D          |
| Kolumnbredd                 | 5   | 30   | 14     | 14           | 14    | 14           |

## <a name="restricting-a-row-to-a-specific-reporting-unit"></a>Begränsa en rad till en specifik rapportenhet
När en rapportrad begränsas till en viss rapportenhet, visar den raden länkade data för den namngivna rapportenheten och ignorera data för andra rapportenheter i rapportträdet. Du kan till exempel skapa en rad som innehåller information för de totala driftskostnaderna för en viss avdelning. Din rapporten kan innehålla dubbla data om rapporten både innehåller ett rapportträd och en raddefinition som har mer än bara det naturliga kontot. Du kan till exempel ha ett rapportträd med de sex avdelningarna i din organisation och du har också en raddefinition som anger en viss kombination av ett konto och en avdelning i raden. När du genererar rapporten skrivs den specifika kombinationen av ett konto och en avdelning ut för varje nivå i rapportträdet, även om den avdelningen kanske inte går att matcha med det som finns i trädet. Detta beteende inträffar eftersom raden åsidosätter vad som normalt filtreras ut av rapportdefinitionen. Ett sätt för att undvika fördubbling av data, är genom att begränsa en rad i en specifik rapportenhet. **Obs!** Om en rad innehåller dimensioner och du begränsar den raden i en underordnad rapportenhet inkluderas radbeloppet för den underordnade enheten och för dess överordnade enheter, men inget fördubbling inträffar.

### <a name="restrict-a-row-to-a-reporting-unit"></a>Begränsa en radkolumn i en rapportenhet

1.  I Rapportdesignern, klicka på **Raddefinitioner** och välj sedan en raddefinition för att ändra.
2.  Dubbelklicka på lämplig cell för **Relaterade formler/rader/enheter**.
3.  I dialogrutan **Val av rapporteringsenhet** i fältet **Rapportträd** väljer du det träd som är tilldelat i rapportdefinitionen.
4.  Välj en rapportenhet och klicka sedan på **OK**. Begränsningen visas i raddefinitionens cell.
5.  Dubbelklicka på cellen i kolumnen **Länk till ekonomiska dimensioner** i den begränsade raden och ange sedan en länk till det ekonomiska datasystemet.

## <a name="selecting-print-control-in-a-row-definition"></a>Välja utskriftskontroll i en raddefinition
Du kan ange utskriftskontrollkoder för varje kolumn genom att använda cellen **Utskriftskontroll**.

### <a name="add-print-control-codes-to-a-report-row"></a>Lägg till utskriftskontrollkoder till en radrapport

1.  Öppna raddefinitionen i Report Designer för att ändra den.
2.  Dubbelklicka på cellen **Utskriftskontroll**.
3.  I dialogrutan **Utskriftskontroll** väljer du en utskriftskontrollkod eller trycker och håller ned CTRL-tangenten om du vill markera flera koder i dialogrutan. Du kan också skriva utskriftskontrollkoder direkt i cellen **Utskriftskontroll** Använd kommatecken för att åtskilja flera utskriftskontrollkoder.
4.  Välj något villkorsstyrda utskriftsalternativ.
5.  Klicka på **OK**.

### <a name="regular-print-control-codes"></a>Vanliga utskriftskontrollkoder

I tabellen nedan beskrivs de vanliga utskriftskontrollkoderna för en raddefinition.

| Skriv ut utskriftskontrollkod | Tolkning av utskriftskontrollkoden         | Beskrivning                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------|--------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NP                 | Icke utskriftsbara rader                                 | Förhindra att beloppen i raden skrivs ut i rapporten och exkludera beloppen från beräkningar. Mer information finns i kolumnen direkt i beräkningsformeln om du vill inkludera icke utskriftsbara kolumner i beräkningen. Exempelvis inkluderas den icke utskriftsbara raden 240 i följande formel: **230+240+250**. Men den icke utskriftsbara raden 240 inkluderas inte i följande formel: **230:250**. |
| CS                 | Valutasymbol; använd valutaformat i den här raden | Inkludera valutasymbolen i alla belopp som inte är procentsatser. Procentsatsvärden tar aldrig emot en valutasymbol.                                                                                                                                                                                                                                                                                                |
| XD                 | Undertryck raden i kontodetaljrapport            | Undertryck visningen av konton i kontodetaljrapporter och transaktiondetaljrapporter. Den här utskriftskontrollen är användbar när en rad innehåller flera konton som inte ska anges på kontodetaljrapporten eller transaktiondetaljrapporten.                                                                                                                                                           |
| X0                 | Undertryck raden om alla nollor                        | Exkludera en rad från rapporten om alla celler i den raden är antingen tomma eller innehåller nollor. Den här utskriftskontrollen är bara meningsfull när alternativet att undertrycka nollsaldo inte markeras i rapportdefinitionen.                                                                                                                                                                                            |
| B0                 | Lämna nollkolumner tomma                         | Lämna kolumner tomma i en rad som innehåller nollbelopp.                                                                                                                                                                                                                                                                                                                                                      |
| XR                 | Undertryck ackumulerade                                  | Undertryck ackumulerade. Om rapporten använder ett rapportträd, är beloppen i denna rad inte ackumulerade till överordnade noder.                                                                                                                                                                                                                                                                               |
| SR                 | Undertryck avrundning                                | Förhindra beloppen i denna rad från att avrundas.                                                                                                                                                                                                                                                                                                                                                          |
| XT                 | Undertryck raden i transaktionsdetaljrapporten        | Undertryck visningen av transaktioner för transaktiondetaljrapporter. Den här utskriftskontrollen är användbar när en rad innehåller flera konton som inte ska anges på en transaktiondetaljrapport.                                                                                                                                                                                                             |

### <a name="conditional-print-control-codes"></a>Villkorsstyrda utskriftskontrollkoder

I tabellen nedan beskrivs vilkorsstyrda utskriftskontrollkoder för en raddefinition.

| Skriv ut utskriftskontrollkod | Beskrivning                                  |
|--------------------|----------------------------------------------|
| (ingen)             | Rensa det villkorsstyrda utskriftsvalet.       |
| DR                 | Skriv endast ut debetsaldona för den här raden.  |
| CR                 | Skriv endast ut kreditsaldona för den här raden. |

## <a name="column-restriction-cell-in-a-row-definition"></a>Cellen Kolumnbegränsning i en raddefinition
Cellen **Kolumnbegränsning** i en raddefinition har flera syften. Beroende på vilken typ av rad kan du använda cellen **Kolumnbegränsning** för att ange en av följande funktioner:

-   Cellen kan begränsa utskriften av radbelopp till en viss kolumn. Den här funktionen är praktiskt, om du skapar en balansräkning i tabellform.
-   Cellen kan ange kolumnen med belopp att sortera.

## <a name="using-a-calculation-formula-in-a-row-definition"></a>Använda en beräkningsformel i en raddefinition
En beräkningsformel i en raddefinition kan innehålla operatorerna **+**, **-**, **\*** och **/**, samt även uttrycket **IF/THEN/ELSE**. Dessutom kan gälla en beräkning omfatta enskilda celler och absoluta belopp (faktiska nummer som är inkluderade i formeln). Formeln kan innehålla upp till 1 024 tecken. Beräkningar kan inte tillämpas på de rader som innehåller celler av typen **Länk till ekonomiska dimensioner** (FD). Du kan emellertid inkludera beräkningar för varandra följande rader, undertrycka utskrift av dessa rader och sedan summera beräkningsraderna.

### <a name="operators-in-a-calculation-formula"></a>Operatorer i en beräkningsformel

En beräkningsformel använder mer komplexa operatorer än en radsummaformel. Du kan däremot använda operatorerna **\*** och **/** tillsammans med de ytterligare operatorerna som ska multiplicera (\*) och dividera (/) belopp. Om du vill använda ett intervall eller en summa i en beräkningsformel måste du använda ett @-tecken (@) framför alla radkoder om du inte använder en kolumn i raddefinitionen. Om du till exempel vill lägga till beloppet i rad 100 till beloppet i rad 330, kan du använda radsummeformeln **100+330** eller beräkningsformeln **@100+@330**. **Obs!** Du måste använda ett @-tecken för varje radkod som du använder i en beräkningsformel. Annars kan numret läsas som ett absolut belopp. Formeln **@100+330** lägger exempelvis till 330 dollar till beloppet i rad 100. När du refererar till en kolumn i en beräkningsformel krävs inget tecken (@).

### <a name="create-a-calculation-formula"></a>Skapa en beräkningsformel

1.  I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.
2.  Dubbelklicka på cellen **Formatkod** och markera sedan **CAL**.
3.  Skriv in beräkningsformeln i cellen **Relaterade formler/rader/enheter**.

### <a name="example-of-a-calculation-formula-for-specific-rows"></a>Exempel på en beräkningsformel för specifika rader

I det här exemplet betyder beräkningsformeln **@100+@330** att beloppet på rad 100 läggs till beloppet på rad 330. Radsummeformeln **340 + 370** tillför beloppet på rad 370 till beloppet på rad 340. (Beloppet på rad 370 är beloppet från beräkningsformeln.)

| Radkod | Beskrivning                 | Formatkod | Relaterade formler/rader/enheter | Utskriftskontroll | Radmodifierare | Länk till ekonomiska dimensioner |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Likvida medel vid periodens början |             |                            | NP            | BB           | +Konto=\[1100:1110\]       |
| 370      | Likvida medel vid årets början   | CAL         | @100+@330                  | NP            |              |                              |
| 400      | Likvida medel vid periodens början | TOT         | 340+370                    |               |              |                              |

När definitionen för raden har en formatkod på **CAL**, och du anger en matematisk beräkning i cellen **Relaterade formler/rader/enheter** måste du även ange bokstaven för associerade kolumnen och raden i rapporten. Ange till exempel **A.120** för att representera kolumn A, rad 120. Alternativt kan du också använda ett snabel-a (@) för att visa alla kolumner. Ange till exempel **@120** för att representera alla kolumner i rad 120. En matematisk beräkning som inte har någon kolumnbokstav eller ett snabel-a (@) antas vara ett reellt tal. **Obs!** Om du använder en etikettradkod för att referera till en rad, måste du använda en punkt (.) som avgränsare mellan kolumnbokstaven och etiketten (t.ex. **A.GROSS\_MARGIN/A.SALES**). Om du använder ett snabel-a (@) krävs ingen avgränsare (till exempel **@GROSS\_MARGIN/@SALES**).

### <a name="example-of-a-calculation-formula-for-a-specific-column"></a>Exempel på en beräkningsformel för en specifik kolumn

I det här exemplet innebär beräkningsformeln **E=C.340** att beräkningen cellen i kolumn C, rad 340, bara utförs på kolumn E. **Obs!** När du refererar till en kolumn i en beräkningsformel krävs inget @-tecken.

| Radkod | Beskrivning                 | Formatkod | Relaterade formler/rader/enheter | Utskriftskontroll | Radmodifierare | Länk till ekonomiska dimensioner |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Likvida medel vid periodens början |             |                            | NP            | BB           | +Konto=\[1100:1110\]       |
| 370      | Likvida medel vid årets början   | CAL         | E=C.340                    | NP            |              |                              |
| 400      | Likvida medel vid periodens början | TOT         | 340+370                    |               |              |                              |

### <a name="modifying-a-number-in-selected-columns"></a>Ändra ett nummer i valda kolumner

Om du ändrar ett nummer eller en beräkning i en kolumn för en särskild rad men inte vill att andra kolumner i rapporten ska påverkas kan du ange **CAL** (beräkning) i kolumnen **Formatkod** i raddefinitionen.

-   Om du vill utföra en beräkning för alla rapportkolumner (**FD**) anger du inte någon kolumntilldelning.
-   Om du vill begränsa en formel till specifika kolumner anger du kolumnbokstaven, ett likhetstecken (**=**), och därefter formeln.
-   Du kan ange flera kolumner. När du använder ett @-tecken med en specifik kolumnplacering, är @-tecknet relaterat till raden.
-   Du kan ange flera kolumnformler på en rad. Separera formler genom att använda kommatecken.

### <a name="calculation-examples"></a>Beräkningsexempel

| Beräkning            | Åtgärd som skapas                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------|
| @130\*.75              | För varje kolumn multipliceras värdet på rad 130 med 0,75. Resultatet infogas sedan i den aktuella raden för varje kolumn. |
| B=@130\*.75            | Samma beräkningen utförs bara på kolumn B.                                                                      |
| A,B,C=(@100/@130)\*.75 | A=(A.100/A.130)\*.75 B=(B.100/B.130)\*.75 C=(C.100/C.130)\*.75                                                           |

### <a name="ifthenelse-statements-in-a-row-definition"></a>IF/THEN/ELSE-utdrag i en raddefinition

**IF/THEN/ELSE**-utdrag kan läggas till en giltig beräkning och användas med **CAL**-formatet. Du anger beräkningsformeln **IF/THEN/ELSE** i cellen i kolumnen **Relaterade formler/rader/enheter**. Beräkningsformler med **IF/THEN/ELSE** använder följande format: IF &lt;sant/falskt-uttryck&gt; THEN &lt;formel&gt; ELSE &lt;formel&gt; The **ELSE &lt;formel&gt;**-delen av uttrycket är valfri.

#### <a name="if-statements"></a>IF-utdrag

Utdraget som följer **IF**-utdraget kan utgöras av alla utdrag som kan utvärderas som sant eller falskt. Utdraget som följer **IF**-utdraget kan inkludera en enskild utvärdering eller så den kan vara ett komplext utdrag som kan innehålla flera uttryck. Nedan följer några exempel:

-   **IF A.200&gt;0** (enkel utvärdering)
-   **IF A.200&gt;0 OCH A.200&lt;10,000** (komplext uttryck)
-   **IF A.200&gt;10000 ELLER ((A.340/B.1200)\*2 &lt;1200)** (komplext uttryck som innehåller flera olika uttryck)

Begreppet **Perioder** i ett **IF**-utdrag representerar antalet perioder för rapporten. Den termen används vanligtvis för att beräkna ett medelvärde hittills i år. När du kör en rapport för perioden 7 YTD, innebär utdraget **B.150/Perioder** att värdet i rad 150 i kolumnen B delas med 7.

#### <a name="then-and-else-formulas"></a>THEN- och ELSE-formler

Formlerna **THEN** och **ELSE** kan vara en giltig beräkning, från mycket enkla värdetilldelningar till komplexa formler. Uttrycket **IF A.200&gt;0 THEN A=B.200** betyder exempelvis: "Om värdet i cellen i kolumn A för rad 200 är mer än 0 (noll), ange värdet från cellen i kolumnen B för rad 200 i cellen i kolumn A för den aktuella raden". Det tidigare utdraget **IF/THEN** sätter ett värde i en kolumn för den aktuella raden. Du kan emellertid också använda ett @-tecken i antingen sant/falskt-utvärderingar eller formeln för att representera alla kolumner. Nedan följer några andra exempel som beskrivs i följande avsnitt:

-   **IF A.200 &gt;0 THEN B.200**: Om värdet i cellen A.200 är positivt, infogas värdet från cellen B.200 i varje kolumn med den aktuella raden.
-   **IF A.200 &gt;0 THEN @200**: Om värdet i cell A.200 är positivt, infogas värdet från varje kolumn i rad 200 i motsvarande kolumn i den aktuella raden.
-   **IF @200 &gt;0 THEN @200**: Om värdet i rad 200 för den aktuella kolumnen är positivt, infogas värdet från rad 200 i samma kolumn i den aktuella raden.

### <a name="restricting-a-calculation-to-a-reporting-unit-in-a-row-definition"></a>Begränsa en beräkning till en rapportenhet i en raddefinition

Om du vill begränsa en beräkning för en enskild rapporteringsenhet i ett rapportträd, så att det resulterande beloppet inte ackumuleras till en högre nivåenhet, kan du använda koden **@Unit** i cellen **Relaterade formler/rader/enheter** i raddefinitionen. Koden **@Unit** anges i kolumn B i rapportträdet, **Enhetsnamn**. När du använder koden **@Unit** ackumuleras inte värdena, men beräkningen utvärderas i varje nivå i rapportträdet. **Obs!** Om du vill använda denna funktion, måste ett rapportträd associeras till raddefinitionen. Beräkningsraden kan referera till en beräkningsrad eller till en ekonomisk datarad. Beräkningen registreras i cellen **Relaterade formler/rader/enheter** i raddefinitionen och den ekonomiska data-typbegränsningen. Beräkningen måste använda en villkorsstyrd beräkning som inleds med en **IF @Unit**-konstruktion. Här följer ett exempel: IF @Unit(SALES) THEN @100 ELSE 0 Denna beräkning innehåller beloppet från rad 100 i varje kolumn av rapporten, men bara för försäljningsenheten (SALES). Om flera enheter kallas FÖRSÄLJNING kommer beloppet att visas i var och en av dessa enheter. Eventuellt kan rad 100 vara en ekonomisk datarad och kan definieras som icke utskriftsbar. I detta fall förhindras beloppet från att visas i alla enheter i trädet. Du kan även begränsa beloppet till en viss kolumn i rapporten, till exempel kolumn H, med hjälp av en kolumnbegränsning om du bara vill skriva ut värdet i den kolumnen i rapporten. Du kan inkludera **OR**-kombinationer i ett **IF**-utdrag. Här följer ett exempel: IF @Unit(SALES) OR @Unit(SALESWEST) THEN 5 ELSE @100 Du kan ange en enhet i en begränsning av beräkningstyp på något av följande sätt:

-   Ange ett enhetsnamn om du vill inkludera enheter som matchar. **IF @Unit(SALES)**  möjliggör exempelvis beräkningen för alla enheter som bär namnet SALES, även om det finns flera SALES-enheter i rapportträdet.
-   Ange företags- och enhetsnamn för att begränsa beräkningen till specifika enheter i ett visst företag. Ange t.ex. **IF @Unit(ACME:SALES**) för att begränsa beräkningen till försäljningsenheter (SALES) i ACME-företag.
-   Ange fullständig hierarkikod från rapportträdet för att begränsa beräkningen till en viss enhet. Ange till exempel **IF @Unit(SUMMARY^ACME^WEST COAST^SALES)**. **Obs!** För att hitta den fullständiga hierarkikoden högerklickar du i rapportträddefinitionen och väljer sedan **Kopiera rapportenhetsidentifierare (H-kod)**.

#### <a name="restrict-a-calculation-to-a-reporting-unit"></a>Begränsa en beräkning i en rapportenhet

1.  I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.
2.  Dubbelklicka på cellen **Formatkod** och markera sedan **CAL**.
3.  Klicka på cellen **Relaterade formler/rader/enheter** och ange sedan en villkorsstyrd beräkning som inleds med en **OM @Unit**-konstruktion.

### <a name="ifthenelse-statements-in-a-column-definition"></a>IF/THEN/ELSE-utdrag i en kolumndefinition

Ett **IF/THEN/ELSE**-utdrag gör att en beräkning är beroende av resultaten från en annan kolumn. Du kan referera till andra kolumner, men du kan inte referera till en rapportcell i **IF**-utdraget. Alla beräkningar måste tillämpas för hela kolumnen. Uttrycket **IF B&gt;100 THEN B ELSE C\*1.25** betyder exempelvis "Om beloppet i kolumn B är mer än 100, infoga värdet från kolumn B till kolumn **CALC**. Om beloppet i kolumn B inte är mer än 100, multiplicerar du värdet i kolumn C med 1,25 och infogar resultatet i kolumn **CALC**." Följ alltid **IF**-utdraget med ett logiskt utdrag som kan utvärderas som sant eller falskt. Formlerna som du använder för både **THEN**-utdraget och **ELSE**-utdraget kan innehålla referenser till ett valfritt antal kolumner och dessa formler kan vara så komplexa som du vill. **Obs!** Du kan inte infoga resultaten av en beräkning till någon annan kolumn. Resultaten måste vara i kolumnen som innehåller formeln.




