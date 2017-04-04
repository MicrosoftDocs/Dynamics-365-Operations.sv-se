---
title: Avancerade formateringsalternativ i ekonomiska rapporter
description: "När du skapar en rapport inom ekonomisk rapportering blir ytterligare formateringsfunktioner tillgängliga, inklusive filter för dimensioner, begränsningar för kolumner och rapportenheter, icke-utskriftsrader samt IF/THEN/ELSE-utdrag i beräkningar."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter
ms.custom: 106571
ms.assetid: 895b5127-01d6-4495-b127-343387b743aa
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 631fec1dc135565e6d38e7faf193a7a898b508cb
ms.lasthandoff: 03/29/2017


---

# <a name="advanced-formatting-options-in-financial-reporting"></a>Avancerade formateringsalternativ i ekonomiska rapporter

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
Om du utformar en rapport ska du först skapa alla detaljrader för att säkerställa att värdena dras in som förväntat. Lägg sedan till **NP** (ingen utskrift) formatåsidosätt för att dölja information som innehåller de senaste värdena. **Viktigt:** När du använder formatkoden **CAL** i raddefinitionen kan du inte gå ner till transaktiondetaljen. Formler för att tvinga, använder du följande format: &lt;målkolumn&gt;=&lt;kommer kolumnen&gt;. &lt;Radkod&gt; avgränsa eventuella ytterligare placeringar för en rad med ett kommatecken och ett blanksteg. Här finns ett exempel: D=C.190 E=C.100

## <a name="examples-of-advanced-formatting-options"></a>Exempel på avancerade formateringsalternativ
Följande exempel visar hur du öppnar raddefinitionen och kolumndefinition om du vill aktivera en grundläggande kassaflödesrapport (exempel 1) och en statistisk rapport (exempel 2) .

### <a name="example-1-basic-forcing"></a>Exempel 1: Grundläggande framtvinga

Följande tabell visar ett exempel på en raddefinition som använder grundläggande framtvingning.

| Radkod | Beskrivning                      | Formatkod | Relaterade formler/rader/enheter | Formatåsidosätt | Normalbalans | Utskriftskontroll | Kolumnbegränsning | Radmodifierare               | Länk till ekonomiska dimensioner |
|----------|----------------------------------|-------------|-----------------------------|-----------------|----------------|---------------|--------------------|----------------------------|------------------------------|
| 100      | Likvida medel vid periodens början (NP) |             |                             |                 |                |               |                    | Konto modifierare = \[/BB\] | + Segment2 = \[1100\]         |
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
| 190      | USA-försäljningar                  |             |                                 |                      | C              |               |                    |              | + Segment2 = \[41\*\], Segment3 = \[00\]    |
| 220      | Internationell försäljning       |             |                                 |                      | C              |               |                    |              | + Segment2 = \[41\*\], Segment3 = \[01:99\] |
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
En beräkningsformel i en raddefinition kan innehålla den **+**, **-**, **\***, och **/**operatorer samt **IF/THEN/ELSE** utdrag. Dessutom kan gälla en beräkning omfatta enskilda celler och absoluta belopp (faktiska nummer som är inkluderade i formeln). Formeln kan innehålla upp till 1 024 tecken. Beräkningar kan inte tillämpas på de rader som innehåller celler av typen **Länk till ekonomiska dimensioner** (FD). Du kan emellertid inkludera beräkningar för varandra följande rader, undertrycka utskrift av dessa rader och sedan summera beräkningsraderna.

### <a name="operators-in-a-calculation-formula"></a>Operatorer i en beräkningsformel

En beräkningsformel använder mer komplexa operatorer än en radsummaformel. Kan du använda den **\***och **/**operatorer tillsammans med ytterligare operatorer att multiplicera (\*) och dividera belopp (/). Om du vill använda ett intervall eller en summa i en beräkningsformel måste du använda ett @-tecken (@) framför alla radkoder om du inte använder en kolumn i raddefinitionen. Om du vill lägga till beloppet på rad 100 beloppet på rad 330 du exempelvis använda radsummaformeln **100 + 330** eller beräkningsformeln **@100+@330**. **Obs!** Du måste använda ett @-tecken för varje radkod som du använder i en beräkningsformel. Annars kan numret läsas som ett absolut belopp. Exempelvis formeln **@100+330** USD 330 läggs till beloppet på rad 100. När du refererar till en kolumn i en beräkningsformel krävs inget tecken (@).

### <a name="create-a-calculation-formula"></a>Skapa en beräkningsformel

1.  I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.
2.  Dubbelklicka på cellen **Formatkod** och markera sedan **CAL**.
3.  Skriv in beräkningsformeln i cellen **Relaterade formler/rader/enheter**.

### <a name="example-of-a-calculation-formula-for-specific-rows"></a>Exempel på en beräkningsformel för specifika rader

I det här exemplet beräkningsformeln **@100+@330** innebär att beloppet på rad 100 läggs till beloppet på rad 330. Radsummaformeln **340 + 370** beloppet på rad 370 adderar summan i rad 340. (Beloppet på rad 370 är beloppet från beräkningsformeln.)

| Radkod | Beskrivning                 | Formatkod | Relaterade formler/rader/enheter | Utskriftskontroll | Radmodifierare | Länk till ekonomiska dimensioner |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Likvida medel vid periodens början |             |                            | NP            | BB           | + Konto =\[1100:1110\]       |
| 370      | Likvida medel vid årets början   | CAL         | @100+@330                  | NP            |              |                              |
| 400      | Likvida medel vid periodens början | TOT         | 340+370                    |               |              |                              |

När definitionen för raden har en formatkod på **CAL**, och du anger en matematisk beräkning i cellen **Relaterade formler/rader/enheter** måste du även ange bokstaven för associerade kolumnen och raden i rapporten. Till exempel anger **A.120** som representerar kolumn A, rad 120. Du kan också använda ett snabel-a (@) att visa alla kolumner. Till exempel anger **@120**som representerar alla kolumner i rad 120. En matematisk beräkning som inte har en kolumnbokstaven eller ett snabel-a (@) antas är ett decimaltal. **Anmärkning:** om du använder en etikett Radkod för att referera till en rad, måste du använda en punkt (.) som avgränsare mellan kolumnbokstaven och etiketten (t.ex, **A.GROSS\_MARGIN/A.SALES**). Om du använder ett snabel-a (@), avgränsare behövs inte efter uppgraderingen (t.ex, **@GROSS\_MARGIN/@SALES**).

### <a name="example-of-a-calculation-formula-for-a-specific-column"></a>Exempel på en beräkningsformel för en specifik kolumn

I det här exemplet innebär beräkningsformeln **E=C.340** att beräkningen cellen i kolumn C, rad 340, bara utförs på kolumn E. **Obs!** När du refererar till en kolumn i en beräkningsformel krävs inget @-tecken.

| Radkod | Beskrivning                 | Formatkod | Relaterade formler/rader/enheter | Utskriftskontroll | Radmodifierare | Länk till ekonomiska dimensioner |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Likvida medel vid periodens början |             |                            | NP            | BB           | + Konto =\[1100:1110\]       |
| 370      | Likvida medel vid årets början   | CAL         | E=C.340                    | NP            |              |                              |
| 400      | Likvida medel vid periodens början | TOT         | 340+370                    |               |              |                              |

### <a name="modifying-a-number-in-selected-columns"></a>Ändra ett nummer i valda kolumner

Om du ändrar ett nummer eller en beräkning i en kolumn för en särskild rad men inte vill att andra kolumner i rapporten ska påverkas kan du ange **CAL** (beräkning) i kolumnen **Formatkod** i raddefinitionen.

-   Om du vill utföra en beräkning för alla rapportkolumner (**FD**) anger du inte någon kolumntilldelning.
-   Om du vill begränsa en formel till specifika kolumner anger du kolumnbokstaven, likhetstecken (**=**), och sedan formeln.
-   Du kan ange flera kolumner. När du använder ett @-tecken med en specifik kolumnplacering, är @-tecknet relaterat till raden.
-   Du kan ange flera kolumnformler på en rad. Separera formler genom att använda kommatecken.

### <a name="calculation-examples"></a>Beräkningsexempel

| Beräkning            | Åtgärd som skapas                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------|
| @130\*.75              | För varje kolumn multipliceras värdet på rad 130 med 0,75. Resultatet infogas sedan i den aktuella raden för varje kolumn. |
| B=@130\*.75            | Samma beräkningen utförs bara på kolumn B.                                                                      |
| A, B,C=(@100/@130)\*.75 | A=(A.100/A.130)\*B=(B.100/B.130).75\*.75 C=(C.100/C.130)\*.75                                                           |

### <a name="ifthenelse-statements-in-a-row-definition"></a>IF/THEN/ELSE-utdrag i en raddefinition

**IF/THEN/ELSE**-utdrag kan läggas till en giltig beräkning och användas med **CAL**-formatet. Du anger beräkningsformeln **IF/THEN/ELSE** i cellen i kolumnen **Relaterade formler/rader/enheter**. **IF/THEN/ELSE** beräkning för formler används följande format: om &lt;SANT/FALSKT-uttryck&gt; sedan &lt;formeln&gt; ELSE &lt;formeln&gt; de **ELSE &lt;formeln&gt;** utdraget är valfritt.

#### <a name="if-statements"></a>IF-utdrag

Utdraget som följer **IF**-utdraget kan utgöras av alla utdrag som kan utvärderas som sant eller falskt. Utdraget som följer **IF**-utdraget kan inkludera en enskild utvärdering eller så den kan vara ett komplext utdrag som kan innehålla flera uttryck. Nedan följer några exempel:

-   **IF A.200&gt;0** (enkel utvärdering)
-   **IF A.200&gt;0 AND A.200&lt;10 000** (komplexa uttryck)
-   **IF A.200&gt;10000 eller ((A.340/B.1200)\*2 &lt;1200)** (komplexa uttryck som innehåller flera uttryck)

Begreppet **Perioder** i ett **IF**-utdrag representerar antalet perioder för rapporten. Den termen används vanligtvis för att beräkna ett medelvärde hittills i år. När du kör en rapport för perioden 7 YTD, innebär utdraget **B.150/Perioder** att värdet i rad 150 i kolumnen B delas med 7.

#### <a name="then-and-else-formulas"></a>THEN- och ELSE-formler

Formlerna **THEN** och **ELSE** kan vara en giltig beräkning, från mycket enkla värdetilldelningar till komplexa formler. Till exempel uttrycket **om A.200&gt;0 THEN A=B.200** innebär "om värdet i cell i kolumn A på rad 200 mer än 0 (noll), läggs värdet i cellen i kolumn B i rad 200 i cellen i kolumn A i den aktuella raden." Det tidigare utdraget **IF/THEN** sätter ett värde i en kolumn för den aktuella raden. Du kan emellertid också använda ett @-tecken i antingen sant/falskt-utvärderingar eller formeln för att representera alla kolumner. Nedan följer några andra exempel som beskrivs i följande avsnitt:

-   **IF A.200 &gt;0 THEN B.200**: Om värdet i cell A.200 är ett positivt värde från cell B.200 övergår till alla kolumner på den aktuella raden.
-   **IF A.200 &gt;sedan 0 @200**: Om värdet i cell A.200 är ett positivt värde i varje kolumn i rad 200 placeras i motsvarande kolumn i den aktuella raden.
-   **IF @200&gt;sedan 0 @200**: Om värdet på rad 200 i den aktuella kolumnen är ett positivt värde från rad 200 placeras i samma kolumn på den aktuella raden.

### <a name="restricting-a-calculation-to-a-reporting-unit-in-a-row-definition"></a>Begränsa en beräkning till en rapportenhet i en raddefinition

Om du vill begränsa en beräkning till en enda Rapporteringsenheten i träd, så att det resulterande beloppet inte slås samman med en överordnad enhet, som du kan använda den **@Unit**kod i den **Närliggande formler, rader eller enheter** cell i raddefinitionen. Den **@Unit**kod visas i kolumn B i trädet rapportering, **enhetsnamn**. När du använder den **@Unit**, inte upplyfta värden, men beräkningen utvärderas på varje nivå i trädet rapportering. **Obs!** Om du vill använda denna funktion, måste ett rapportträd associeras till raddefinitionen. Beräkningsraden kan referera till en beräkningsrad eller till en ekonomisk datarad. Beräkningen registreras i cellen **Relaterade formler/rader/enheter** i raddefinitionen och den ekonomiska data-typbegränsningen. Beräkningen måste använda villkorliga beräkning som börjar med en **om @Unit**konstruktion. Här följer ett exempel: om @Unit(försäljning) sedan @1000 ELSE beräkningen innehåller beloppet från rad 100 i varje kolumn i rapporten, men endast för försäljningsenheten. Om flera enheter kallas FÖRSÄLJNING kommer beloppet att visas i var och en av dessa enheter. Eventuellt kan rad 100 vara en ekonomisk datarad och kan definieras som icke utskriftsbar. I detta fall förhindras beloppet från att visas i alla enheter i trädet. Du kan även begränsa beloppet till en viss kolumn i rapporten, till exempel kolumn H, med hjälp av en kolumnbegränsning om du bara vill skriva ut värdet i den kolumnen i rapporten. Du kan inkludera **OR**-kombinationer i ett **IF**-utdrag. Här följer ett exempel: om @Unit(försäljning) eller @Unit(SALESWEST) sedan 5 ELSE @100kan du ange en enhet i en beräkningsbegränsning i något av följande sätt:

-   Ange ett enhetsnamn om du vill inkludera enheter som matchar. Till exempel **om @Unit(försäljning)** gör det möjligt för beräkning av alla enheter med namnet Försäljning, även om det finns flera enheter för försäljning i rapportträdet.
-   Ange företags- och enhetsnamn för att begränsa beräkningen till specifika enheter i ett visst företag. Till exempel anger **om @Unit(ACME försäljning:**) att begränsa beräkningen till försäljning enheter i företaget företag.
-   Ange fullständig hierarkikod från rapportträdet för att begränsa beräkningen till en viss enhet. Till exempel anger **om @Unit(sammanfattning ^ ABC ^ WEST COAST ^ försäljning)**. **Obs!** För att hitta den fullständiga hierarkikoden högerklickar du i rapportträddefinitionen och väljer sedan **Kopiera rapportenhetsidentifierare (H-kod)**.

#### <a name="restrict-a-calculation-to-a-reporting-unit"></a>Begränsa en beräkning i en rapportenhet

1.  I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.
2.  Dubbelklicka på cellen **Formatkod** och markera sedan **CAL**.
3.  Klicka på den **Närliggande formler, rader eller enheter** cell och anger en villkorlig beräkning som börjar med en **om @Unit**konstruktion.

### <a name="ifthenelse-statements-in-a-column-definition"></a>IF/THEN/ELSE-utdrag i en kolumndefinition

Ett **IF/THEN/ELSE**-utdrag gör att en beräkning är beroende av resultaten från en annan kolumn. Du kan referera till andra kolumner, men du kan inte referera till en rapportcell i **IF**-utdraget. Alla beräkningar måste tillämpas för hela kolumnen. Till exempel uttrycket **IF B&gt;100 och annan B C\*1,25** innebär "om beloppet i kolumn B är mer än 100, skriver du värdet från kolumn B i den **BERÄKNA** kolumn. Om beloppet i kolumn B inte är mer än 100, multiplicerar du värdet i kolumn C med 1,25 och infogar resultatet i kolumn **CALC**." Följ alltid **IF**-utdraget med ett logiskt utdrag som kan utvärderas som sant eller falskt. Formlerna som du använder för både **THEN**-utdraget och **ELSE**-utdraget kan innehålla referenser till ett valfritt antal kolumner och dessa formler kan vara så komplexa som du vill. **Obs!** Du kan inte infoga resultaten av en beräkning till någon annan kolumn. Resultaten måste vara i kolumnen som innehåller formeln.


