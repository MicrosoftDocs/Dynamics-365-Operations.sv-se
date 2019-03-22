---
title: Ändra raddefinitionsceller
description: Det här ämnet innehåller en beskrivning av den information som krävs för varje cell i en raddefinition för en ekonomisk rapport och av hur du anger den informationen.
author: ShylaThompson
manager: AnnBe
ms.date: 02/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 58881
ms.assetid: 0af492df-a84e-450c-8045-78ef1211abaf
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d6f6e94fd8e7ddf92e89fedfab09ef0684505819
ms.sourcegitcommit: eb24b63b10c4d06f7550bba9fbd1910ba2719b0a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2019
ms.locfileid: "379674"
---
# <a name="modify-row-definition-cells"></a>Ändra raddefinitionsceller

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller en beskrivning av den information som krävs för varje cell i en raddefinition för en ekonomisk rapport och av hur du anger den informationen.

## <a name="specify-a-row-code-in-a-row-definition"></a>Ange en radkod i en raddefinition

I raddefinitioner identifierar de nummer eller etiketter som finns i cellen **Radkod** varje rad i raddefinitionen. Du kan ange att radkoden ska referera till data i beräkningar och summor.

### <a name="row-code-requirements"></a>Radkodkrav

En radkod krävs för alla rader. Du kan blanda numeriska, alfanumeriska och upphävda (tomma) radkoder i en raddefinition. Radkoden kan vara ett positivt heltal (under 100 000 000) eller en beskrivande etikett som identifierar den raden. En beskrivande etikett måste följa dessa regler:

- Etiketten måste börja med ett alfabetiskt tecken (a till ö eller Ö till A) och kan vara en kombination av nummer och bokstäver upp till 16 tecken.

    > [!NOTE]
    > En etikett kan inkludera understreck (\_), men inga andra specialtecken tillåts.

- Delen kan inte använda något av följande: word reserverade AND, OR, IF, THEN, ELSE, PERIODS, TO, BASEROW, UNIT, NULL, CPO, eller RPO.

Följande exempel är giltiga radkoder:

- 320
- TL\_NET\_INTÄKTER
- TL\_NET\_94

### <a name="change-a-row-code-in-a-row-definition"></a>Ändra en radkod i en raddefinition

1. Öppna Rapport Designer, klicka på **Raddefinitioner** och öppna sedan den raddefinition som ska modifieras.
2. Ange det nya värdet i cellen i kolumnen **Radkod** i lämplig rad.

### <a name="reset-numeric-row-codes"></a>Återställa numeriska radkoder

1. I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.
2. I menyn **Redigera**, klicka på **Numrera om rader**.
3. I dialektgeog **Numrera om rader**, ange nya värden för den startande radkoden och radkodökningen. Du kan återställa de numeriska radkoderna till jämnt fördelade värden. Rapportdesignern numrerar endast om radkoder som börjar med siffror (exempelvis 130 eller 246). Den numrerar inte om radkoder som börjar med bokstäver (exempelvis INCOME\_93 eller TP0693).

> [!NOTE]
> När du numrerar om radkoder uppdaterar rapportdesignern automatiskt referenserna **TOT** och **CAL**. Om raden **TOT** refererar till ett intervall som startar med radkod 100, och du numrerar om rader som börjar med 90, kommer startreferensen **TOT** att ändras från 100 till 90.

## <a name="add-a-description"></a>Lägg till en beskrivning.
Beskrivningscellen innehåller beskrivningen av de ekonomiska data som finns i raden för rapporten, till exempel "Intäkt” eller "Nettoinkomst". Texten i cellen **Beskrivning** visas i rapporten exakt, som du anger den i raddefinitionen.

> [!NOTE]
> Bredden av kolumnen Beskrivning i rapporten anges i kolumndefinitionen. Om texten i kolumnen **Beskrivning** i raddefinitionen är lång, kontrollera bredden på kolumnen **DESC**. När du använder dialogrutan **Infoga rader från**, är värdena i kolumnen **Beskrivning** segmentvärdena eller dimensionsvärdena från den ekonomiska datan. Du kan lägga till rader om du vill infoga beskrivande text, till exempel en avsnittsrubrik eller en delsumma, samt om du vill lägga till formatering, till exempel en linje före en summarad. Om rapporten omfattar ett rapporteringsträd, kan du inkludera den ytterligare texten som har definierats för rapportenheterna i rapporteringsträdet. Du kan även begränsa den ytterligare texten till en viss rapporteringsenhet.

### <a name="add-the-description-for-a-line-on-a-report"></a>Lägg till beskrivningen för en rad i en rapport

1. I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.
2. Välj cellen **Beskrivning** och ange sedan namnet på rapportraden.
3. Tillämpa formatering.

### <a name="add-additional-text-from-a-reporting-tree-in-the-description"></a>Lägga till ytterligare text från ett rapporteringsträd i beskrivningen

1. I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.
2. Ange ytterligare textkod och en annan text i rätt cell för **Beskrivning**.
3. Tillämpa formatering.

### <a name="limit-the-additional-text-to-a-specific-reporting-unit"></a>Begränsa den ytterligare texten till en viss rapporteringsenhet.

1. I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.
2. Hitta raden där ytterligare text ska skapas och dubbelklicka sedan cellen i kolumnen **Relaterade formel/rader/enheter**.
3. Välj diaglogrutan **Val av rapportenhet** i fältet **Rapporteringsträd**.
4. I fältet **Välj rapportenhet för begränsning** visa eller dölj rapporteringsträdet och välj sedan en rapportenhet.

## <a name="add-a-format-code"></a>Lägg till en formatkod
Cellen **Formatkod** ger ett urval av förformaterade val för innehållet i den raden. Om cellen **Formatkod** är tom, tolkas raden som en ekonomisk datadetaljrad.

> [!NOTE]
> Om en rapport innehåller formateringsrader utan belopp som är relaterade till beloppsrader som har ignorerats (t.ex. på grund av nollsaldon), kan du använda kolumnen **Relaterade formler/rader/enheter** för att förhindra att rubriks- och formatrader skrivs ut.

### <a name="add-a-format-code-to-a-report-row"></a>Lägg till en formatkod till en rapportrad

1. I Rapportdesignern, klicka på **Raddefinitioner** och välj sedan en raddefinition för att ändra.
2. Dubbelklicka på cellen **Formatera kod**.
3. Välj en formatkod i listan . Följande tabell beskriver formatkoder och deras åtgärder.

    | Formatkod                   | Tolkning av formatkod | Åtgärd |
    |-------------------------------|-----------------------------------|--------|
    | (Ingen)                        |                                   | Rensar cellen **Formatkod**. |
    | TOT                           | Summa                             | Identifierar en rad som använder matematiska operatorer i kolumnen **Relaterade formler/rader/enheter**. Summor innehåller enkla operatorer som t.ex. **+** eller **-**. |
    | CAL                           | Beräkning                       | Identifierar en rad som använder matematiska operatorer i kolumnen **Relaterade formler/rader/enheter**. Beräkningar innehåller komplexa operatorer, t.ex. **+**, **-**, **\***, **/** och uttrycken **IF/THEN/ELSE**. |
    | DES                           | beskrivning                       | Identifierar en rubrikrad eller en tom rad i en rapport. |
    | LFT RGT CEN                   | Vänster Höger Centrera                 | Justerar radbeskrivningstexten på rapportsidan, oavsett textens placering i kolumndefinitionen. |
    | CBR                           | Ändra basrad                   | Identifierar en rad som anger basraden för kolumnberäkningar. |
    | KOLUMN                        | Kolumnavbrott                      | Startar en ny kolumn i rapporten. |
    | SIDA                          | Sidbrytning                        | Startar en ny sida i rapporten. |
    | \---                          | Enkel understrykning                  | Sätter en enskild rad under alla beloppskolumner i rapporten. |
    | ===                           | Dubbel understrykning                  | Sätter en dubbel rad under alla beloppskolumner i rapporten. |
    | LINE1                         | Tunn rad                         | Drar en enskild tunn rad över sidan. |
    | LINE2                         | Tjock linje                        | Rita en enkel tjock linje över sidan. |
    | LINE3                         | Prickad linje                       | Drar en enskild prickig rad över sidan. |
    | LINE4                         | Tjock rad och tunn rad          | Drar en dubbel rad över sidan. Den övre raden är tjock och den undre är tunn. |
    | LINE5                         | Tunn rad och tjock rad          | Drar en dubbel rad över sidan. Den övre raden är tunn och den undre är tjock. |
    | BXB BXC                       | Inrutad rad                         | Drar en ruta runt rappportraden som börjar med **BXB** och avslutas med raden **BXC**. |
    | REM                           | Kommentar                            | Identifierar en rad som är en kommentarsrad, och därför inte ska skrivas ut på rapporten. En kommentarsrad kan t.ex. innehålla en förklaring av dina formateringsmetoder. |
    | SORT ASORT SORTDESC ASORTDESC | Sortera                              | Sorteringsutgifter eller intäkter sorterar en aktuell rapport eller en budgetavvikelserapport efter den största avvikelsen eller sorterar radbeskrivningarna i alfabetisk ordning. |

## <a name="specify-related-formulasrowsunits"></a>Ange relaterade formler/rader/enheter
Cellen **Relaterade formler/rader/enheter** har flera syften. Beroende på vilken typ av rad kan **Relaterade formler/rader/enheter** utföra någon av följande funktioner:

- Definiera de rader som ska tas med i beräkningen när du använder formatkoden **TOT** eller formatkoden **CAL**.
- Länka en formateringsrad till en beloppsrad så att formateringen skrivs ut om det relaterade beloppet skrivs ut.
- Begränsa en rad till en specifik rapportenhet.
- Definiera basraden för beräkningar när du använder formatkoden **BASEROW**.
- Definiera de rader som du vill sortera när du använder något av sorteringsformatkoderna.

### <a name="use-a-row-total-in-a-row-definition"></a>Använd enradsumma i en raddefinition

Använd en radsummaformel om du vill lägga till eller dra ifrån belopp i andra rader. En formel för att skapa en radsumma kan inkludera operatorerna + och - som kombinerar enskilda rader och intervall. Intervall anges av ett kolon (:). Formeln kan innehålla upp till 1 024 tecken. Här är ett exempel på en standardsummeringsformel: 400+420+430+450+460LIABILITIES+EQUITY520:546520:546-LIABILITIES

### <a name="components-of-a-row-total-formula"></a>Komponenter i en formel för radsumma

När du skapar en formel för radsumma måste du använda radkoder för att ange vilka rader som ska adderas eller subtraheras i den aktuella raddefinitionen. Du måste även ange hur raderna kombineras med operatorer. Summarader och beloppsrader kan användas i alla kombinationer.

> [!NOTE]
> Alla summarader som ligger i en sekvens exkluderas. Om du vill skapa en totalsumma kan du ange intervallet för rader. Om den första raden i ett intervall är en summarad, ingår den raden i den nya summan. Följande tabell beskriver hur operatorer används i radsummaformler.

| Operatör | Exempelformel | beskrivning                                                 |
|----------|-----------------|-------------------------------------------------------------|
| +        | 100+330         | Lägger till beloppet i rad 100 till beloppet i rad 330.        |
| :        | 100:330         | Lägger till summan av alla rader mellan rad 100 och rad 330.    |
| -        | 100-330         | Drar av beloppet i rad 100 från beloppet i rad 330. |

### <a name="create-a-row-total"></a>Skapa en radsumma

1. Klicka på **Raddefinitioner** i Report Designer och öppna den raddefinition som du vill ändra.
2. Dubbelklicka på **Formatkod** i raddefinitionen och välj **TOT**
3. Ange cellen **Relaterade formler/rader/enheter** i summaformeln.

### <a name="relate-a-format-row-to-an-amount-row"></a>Relatera en formatrad till en beloppsrad

I kolumnen **Formatkod** i en raddefinition använder formatkoderna **DES**, **LFT**, **RGT**, **CEN**, **---** och **===** formateringsrader utan belopp. För att undvika denna formatering från att skrivas ut när den relaterade beloppsraden ignoreras (t.ex. för att belopsraderna innehåller nollvärden eller ingen periodaktivitet) måste du relatera formatraderna till motsvarande beloppsrader. Den här funktionen är användbar när du vill förhindra att rubriker eller formatering som är relaterad till delsummor skrivs ut när det inte finns information att skrivas ut för perioden.

> [!NOTE]
> Du kan också förhindra att de detaljerade beloppsraderna skrivs ut, genom att avmarkera alternativet för att visa rader utan belopp. Det här alternativet finns på fliken **Inställningar** i rapportdefinitionen. Som standard ignoreras transaktionsdetaljkonton som har ett nollsaldo eller ingen periodaktivitet i rapporter. För att visa dessa transaktiondetaljkonton, markera kryssrutan **Visa rader utan ett belopp** på fliken **Inställningar** i rapportdefinitionen.

### <a name="relate-a-format-row-to-an-amount-row"></a>Relatera en formatrad till en beloppsrad

1. I Rapportdesignern, klicka på **Raddefinitioner** och välj sedan en raddefinition för att ändra.
2. I formatteringsraden i cellen **Relaterade formler/rader/enheter** anger du radkoden för den beloppsrad som ska ignoreras.

    > [!NOTE]
    > Om du vill utelämna en beloppsrad mycket måste saldot på raden vara 0 (noll). En beloppsrad som har ett saldo ignoreras inte.

3. Klicka på **Spara** på menyn **Arkiv**.

### <a name="example-of-preventing-printing-of-rows"></a>Exempel på att förhindra utskrift av rader

I följande exempel vill Phyllis förhindra att rubriken och understrecken i raden **Totala kontanter** i hennes rapport skrivs ut, eftersom det inte finns någon aktivitet på något av kassakontona. Därför, på rad 220 (som, vilket formatkoden **---** anger, är en formateringsrad), i cellen **Relaterade formler/rader/enheter**, anger hon **250** som är radkoden för beloppsraden som hon vill utelämna.

[![RelatedRowsRowDefinition](./media/relatedrowsrowdefinition-1024x144.png)](./media/relatedrowsrowdefinition.png)

## <a name="select-the-base-row-for-a-column-calculation"></a>Välj basraden för en kolumnberäkning
I relationsrapportering tilldelar du en eller flera basrader i raddefinitionen, med hjälp av formatkoden **CBR** (ändra basrad). En basrad refereras sedan av en beräkning i kolumndefinitionen. Här följer några typiska exempel på CBR-beräkning:

- Procentuell andel av den totala intäkten eftersom den är relaterad till enskilda intäktsartiklar
- Procentuell andel av den totala utgiften eftersom den är relaterad till enskilda utgiftsartiklar
- Procentuell andel av bruttomarginalen eftersom den är relaterad till division- eller avdelningsdetaljer.

En eller flera basrader definieras i raddefinitionen och sedan bestämmer kolumndefinitionen den relation som basraden rapporteras för. Koden som används i kolumnformeln är **BASEROW**. Följande grundläggande matematiska operationer används med **BASEROW**: dividera, multiplicera, addera eller subtrahera. Operationen som används mest divideras med **BASEROW**, där resultatet visas som en procentsats. Kolumnberäkningar som använder **BASEROW** i formeln använder raddefinitionen för den relaterade basraden. **CBR**-rader har följande egenskaper:

- **CBR**-rader skrivs inte ut på den slutförda rapporten.
- **CBR**-formatkoden och dess tillhörande radkod placeras ovanför raden eller avsnittet som visar relaterade beräkningar.

I en kolumndefinition anger kolumntypen **CALC** en kolumn som har en formel i raden **Formel**. Denna formel arbetar med data för den här kolumnen i rapporten och använder nyckelordet Baserow i formatkoderna i raden **CBR**. I raddefinitionen definierar **CBR**-formatkoden basraden för kolumner som beräknar en procentandel av eller multiplicerar med basraden för varje rad i rapporten. Du kan ha flera **CBR**-formatkoder i ett radformat som t.ex. ett för nettoomsättning, ett för bruttoförsäljning och en för totala utgifter. Vanligtvis används **CBR**-formatkoden för att skapa en procentsats för konton som jämförs med en total rad. En basrad används för alla beräkningar tills en annan basrad definieras. Du måste definiera en startande **CBR**-formatkod och en avslutande **CBR**-formatkod. Om du till exempel vill bestämma utgifter som en procentandel av nettoomsättning kan du dela värdet i varje utgiftsrad med värdet i raden för nettoomsättning. I detta fall är raden för nettoomsättning basraden. Du kan definiera en kolumndefinition som rapporterar aktuellt och hittills i år-resultat, tillsammans med basprocentandelen av varje resultat, som visas i följande exempel. Startar med en ingående balans.

### <a name="select-the-base-row-in-a-row-definition-for-a-column-calculation"></a>Välj basraden i raddefinitionen för en kolumnberäkning

1. I Rapportdesignern, klicka på **Kolumnddefinitioner** och öppna kolumndefinitionen för en inkomstredogörelse.
2. Lägg till en ny kolumn i kolumndefinitionen och ange kolumntypen till **CALC**.
3. Ange cellen **Formel** för den nya kolumnen, ange formeln **X/BASEROW**, där **X** är kolumntypen **FD** att visa en procentandel av.
4. Dubbelklicka på cellen **Format/åsidosätt valuta**.
5. I dialogrutan **Formatåsidosätt** i listan **Formatera kategori**, välj **Procent** och klicka sedan på **OK**.
6. På menyn **Fil**, klicka **Spara som** om du sparar kolumndefinitionen under ett nytt namn. Lägg till **CBR** till det aktuella filnamnet (exempelvis **CUR\_YTD\_CBR**). Den här kolumndefinitionen är din kolumndefinition för basrad.
7. I Report Designer, klicka på **Raddefinitioner** och sedan på raddefinitionen för att ändra genom att använda basradberäkning.
8. Infoga en ny rad över raden där basradberäkningen ska starta.
9. Dubbelklicka på cellen **Formatkod** i raddefinitionen och välj sedan **CBR**
10. I cellen **Relaterade formler/rader/enheter** anger du radkodnumret för basraden.

### <a name="example-of-base-row-calculation"></a>Exempel på basradberäkningen

I följande exempel av en raddefinition visar rad 100 att basraden för beräkningar är rad 280.

[![Exempel på basradberäkning.](./media/cbrrowdefinition.png)](./media/cbrrowdefinition.png)

I följande exempel på en kolumndefinition använder beräkningarna formatkoden **CBR**. Beräkningen i kolumnen C har värdet i kolumnen B i rapporten genom värdet på rad 280 i kolumnen B. Formatåsidosättet i kolumnen B skriver ut resultatet av beräkningen som en procentsats. På samma sätt innebär att varje belopp i kolumn E är beloppet i kolumn D som en procentsats av nettoomsättning.

[![Exempel på kolumndefinition.](./media/cbrcolumndefinition2.png)](./media/cbrcolumndefinition2.png)

Följande exempel visar en rapport som kan genereras baserat på de föregående beräkningarna.

[![Exempelrapport baserad på tidigare exempelberäkningar.](./media/cbrreport-1024x272.png)](./media/cbrreport.png)

## <a name="select-a-sorting-code-for-a-row-definition"></a>Välj en sorteringskod för en raddefinition
Sorteringskoder, sorteringkonton eller värden sorterar en aktuell eller budgetavvikelserapport efter den största avvikelsen eller sorterar radbeskrivningarna i alfabetisk ordning. Följande sorteringskoder är tillgängliga:

- **SORT** – Sorterar rapporten i stigande ordning baserat på de angivna värdena i den angivna kolumnen.
- **ASORT** – Sorterar rapporten i stigande ordning baserat på de absoluta värdena i den angivna kolumnen. Med andra ord ignoreras tecknet för varje värde, när värdena sorteras. De här formatkodsekvenserna ordnar värdena efter avvikelsens storlek, oavsett om avvikelsen är positiv eller negativ.
- **SORTDESC** – Sorterar rapporten i fallande ordning baserat på de angivna värdena i kolumnen.
- **ASORTDESC** – Sorterar rapporten i fallande ordning baserat på absolutvärdet av de angivna värdena i kolumnen.

### <a name="select-a-sorting-code"></a>Välj en sorteringskod

1. I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.
2. Dubbelklicka på cellen **Formatkod** och välj sedan en sorteringskod.
3. I cellen **Relaterade formler/rader/enheter** anger du intervallet för radkoderna som ska sorteras. Ange den första radkoden, ett kolon (:) och sedan den senaste radenkod om du vill ange ett intervall. Ange t.ex. **160:490** om vill ange att intervallet är rad 160 genom rad 490.
4. Ange cellen **Kolumnbegränsning**, ange bokstaven på rapportkolumnen som ska användas för sorteringen.

    > [!NOTE]
    > Inkludera endast beloppsrader i sorteringsberäkningen.

### <a name="examples-of-ascending-and-descending-column-values"></a>Exempel på stigande och fallande kolumnvärden

I följande exempel sorteras värdena i rapportkolumnen D i stigande ordning på raderna 160 till 490. Dessutom sorteras de absoluta värdena i rapportkolumnen G i fallande ordning på raderna 610 till 940.

| Radkod | Beskrivning                                         | Formatkod | Relaterade formler/rader/enheter | Standardsaldo | Kolumnbegränsning | Länk till ekonomiska dimensioner |
|----------|-----------------------------------------------------|-------------|-----------------------------|----------------|--------------------|------------------------------|
| 100      | Sorterat efter månatlig avvikelse i stigande ordning       | DES         |                             |                |                    |                              |
| 130      |                                                     | SORT        | 160:490                     |                | D                  |                              |
| 160      | Försäljning                                               |             |                             | C              |                    | 4100                         |
| 190      | Försäljningsreturer                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 490      | Räntainkomst                                     |             |                             | C              |                    | 7000                         |
| 520      |                                                     | DES         |                             |                |                    |                              |
| 550      | Sorterat efter YTD absolut avvikelse i fallande ordning | DES         |                             |                |                    |                              |
| 580      |                                                     | ASORTDESC   | 610:940                     |                | G                  |                              |
| 610      | Försäljning                                               |             |                             | C              |                    | 4100                         |
| 640      | Försäljningsreturer                                       |             |                             |                |                    | 4 110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 940      | Ränteintäkter                                     |             |                             | C              |                    | 7000                         |


## <a name="specify-a-format-override-cell"></a>Ange en cell för Formatåsidosätt
Cellen **Formatåsidosätt** anger formateringen som används för raden när rapporten skrivs ut. Denna formatering åsidosätter den formatering som anges i kolumndefinitionen och rapportdefinitionen. Som standard är formateringen som anges i dessa definitioner valuta. När en rad i rapporten anger antalet tillgångar, till exempel antalet fastigheter och en annan rad anger dessa tillgångars penningvärde kan du åsidosätta valutaformateringen och ange numerisk formatering för raden som anger antalet fastigheter. Du anger denna information i dialogrutan **Formatåsidosätt**. De tillgängliga alternativet beror på formatkategorin som du väljer. Området **Exempel** på dialogrutan visar exempelformat. Följande exportformatkategorier är tillgängliga:

- Valutaformatering
- Numeriskt formatering
- Procentsatsformatering
- Anpassad formatering

### <a name="override-cell-formatting"></a>Åsidosättcellformatering

1. Öppna raddefinitionen i Report Designer för att ändra den.
2. Dubbelklicka på kolumnen **Formatåsidosätt** i den raden som formatet ska åsidosättas för.
3. Välj dialogrutan **Formatåsidosätt**, välj de formateringsalternativ som ska användas för den raden i rapporten.
4. Klicka på **OK**.

### <a name="currency-formatting"></a>Valutaformatering

Valutaformatering gäller för ett räkenskapsbelopp och inkluderar valutasymbolen. Följande alternativ är tillgängliga:

- **Valutasymbol** – Rapportens valutasymbol. Det här värdet åsidosätter inställningen **Nationella alternatv** för företagsinformationen.
- **Negativa nummer** - Negativa nummer kan ha ett minustecken (-), de kan visas inom parentes, eller de kan ha en triangel (∆).
- **Antal decimaler** – Antal siffror som ska visas efter decimaltecknet.
- **Nollvärdeåsidosätttext** – Texten som ska inkluderas i rapporten när beloppet är 0 (noll). Texten visas som sista raden i området **Bildpunkt**.

    > [!NOTE]
    > Om utskrift ignoreras av nollvärden eller ingen periodaktivitet, ignoreras denna text.

### <a name="numeric-formatting"></a>Numeriskt formatering

Numerisk formatering gäller för alla belopp och inkluderar inte en valutasymbol. Följande alternativ är tillgängliga:

- **Negativa nummer** - Negativa nummer kan ha ett minustecken (-), de kan visas inom parentes, eller de kan ha en triangel (∆).
- **Antal decimaler** – Antal siffror som ska visas efter decimaltecknet.
- **Nollvärdeåsidosätttext** – Texten som ska inkluderas i rapporten när beloppet är 0 (noll). Texten visas som sista raden i området **Bildpunkt**.

    > [!NOTE]
    > Om utskrift ignoreras av nollvärden eller ingen periodaktivitet, ignoreras denna text.

### <a name="percentage-formatting"></a>Procentsatsformatering

Procentsatsformatering inkluderar procenttecknet (%). Följande alternativ är tillgängliga:

- **Negativa nummer** - Negativa nummer kan ha ett minustecken (-), de kan visas inom parentes, eller de kan ha en triangel (∆).
- **Antal decimaler** – Antal siffror som ska visas efter decimaltecknet.
- **Nollvärdeåsidosätttext** – Texten som ska inkluderas i rapporten när beloppet är 0 (noll). Texten visas som sista raden i området **Bildpunkt**.

    > [!NOTE]
    > Om utskrift ignoreras av nollvärden eller ingen periodaktivitet, ignoreras denna text.

### <a name="custom-formatting"></a>Anpassad formatering

Använd anpassad formateringkategori om du vill skapa en anpassad formatåsidosättning. Följande alternativ är tillgängliga:

- **Typ** – De anpassade formatet.
- **Nollvärdeåsidosätttext** – Texten som ska inkluderas i rapporten när beloppet är 0 (noll). Texten visas som sista raden i området **Bildpunkt**.

    > [!NOTE]
    > Om utskrift ignoreras av nollvärden eller ingen periodaktivitet, ignoreras denna text.

Typen ska representera det positiva värdet och sedan det negativa värdet. Vanligtvis anger du ett liknande format som särskiljer positiva och negativa värden. Om du t.ex. vill ange att både positiva och negativa värden har två decimaler, men negativa värden visas inom parentes anger du **0.00;(0.00)**. Följande tabell visar anpassade format som du kan använda för att kontrollera formatet för dina värden. Alla exempel startar från värdet 1234.56.

| Format                         | Positivt   | Negativ     | Noll    |
|--------------------------------|------------|--------------|---------|
| 0                              | 1235       | -1235        | 0       |
| 0;0                            | 1235       | 1235         | 0       |
| 0;(0);-                        | 1235       | 1235         | -       |
| \#,\#\#\#;(\#,\#\#\#);""       | 1 235      | (1 235)      | (Tom) |
| \#,\#\#0.00;(\#,\#\#0.00);zero | 1 234,56   | (1 234,56)   | noll    |
| 0,00%;(0,00%)                  | 123 456,00% | (123 456,00%) | 0,00%   |

## <a name="specify-a-normal-balance-cell"></a>Ange en cell för normalt saldo
Cellen **Normalt saldo** i en raddefinition kontrollerar tecknet för beloppen i en rad. Om du vill återställa tecknet för en rad, eller om det normala saldot för ett konto är en kredit, anger du **C** i cellen **Normalt saldo** för raden. Rapportdesigner återför tecknet för alla krediteringssaldokonton i den raden. När rapportdesignern konverterar dessa konton tar den bort debet-/kreditegenskapen från alla belopp och gör därför summeringen okomplicerad. Om du till exempel vill beräkna nettointäkten subtraherar du utgifter från intäkter. Vanligtvis påverkas inte summerade och beräknade rader av **C**-koden. Men Management Reporter **XCR** i kolumndefinitionen återför tecknen för alla rader som innehåller ett **C** i kolumnen **Normalt saldo**. Denna formatering är särskilt viktig när du vill visa alla ofördelaktiga avvikelser som negativa belopp. Om ett summerat eller beräknat nummer har fel tecken anger du ett **C** i **Normalt saldo** för raden att återföra tecknet.

## <a name="specify-a-row-modifier-cell"></a>Ange en radmodifikatorcell
Innehållet i cellen **Radmodifierare** åsidosätter räkenskapsåren, perioder och annan information som angetts i radens kolumndefinition. Den valda modifikatorn gäller för varje konto i raden. Du kan ändra varje rad genom att använda en eller fler av följande typer av modifikatorer:

- Kontomodifierare
- Bokkodsmodifierare
- Konto och transaktionsattribut

### <a name="override-a-column-definition"></a>Åsidosätt en kolumndefinition

1. Öppna raddefinitionen i Report Designer för att ändra den.
2. Dubbelklicka på raden i den cell, där du vill åsidosätta kolumndefinitionen **Radmodifikatorn**.
3. Välj dialogrutan **Radmodifikatorn**, välj ett alternativ i fältet **Kontomodifikator** . Mer information finns i avsnittet ”Kontomodifierare".
4. I fältet **Boka kodmodifikatorn** väljer du bokkoden som ska användas för raden.
5. Under **Attribut**, följ dessa steg om du vill lägga till en post för varje attribut som ska tas med i radkoden:

    1. Dubbelklicka på cellen **Attribut** och välj sedan ett attributnamn.

        > [!IMPORTANT]
        > Ersätt nummertecknet (\#) med ett numeriskt värde.

    2. Dubbelklicka på cellen **Från** och ange det första värdet för intervallet.
    3. Dubbelklicka på cellen **Till** och ange det last värdet för intervallet.

6. Klicka på **OK**.

### <a name="account-modifiers"></a>Kontomodifierare

När du väljer ett visst konto kombinerar rapportdesignern vanligtvis kontot och räkenskapsåret, perioder och annan information som du anger i kolumndefinitionen. Du kan använda olika information, till exempel olika räkenskapsperioder, för specifika detaljrader. I följande tabell visar de kontomodifierare som är tillgängliga. Byt ut nummertecknet (\#) mot ett värde som är lika med eller mindre än antalet perioder i ett räkenskapsår.

| Kontomodifierare | Vad är utskrivet                                                                           |
|------------------|-------------------------------------------------------------------------------------------|
| /BB              | Ingående balans för ett konto.                                                     |
| /\#              | Saldot för den angivna perioden.                                                     |
| /-\#             | Saldot för perioden som är \# perioder före den aktuella perioden.                  |
| /+\#             | Saldot för perioden som är \# perioder efter den aktuella perioden.                   |
| /C               | Saldot för den aktuella perioden.                                                       |
| /C-\#            | Saldot för perioden som är \# perioder före den aktuella perioden.                  |
| /C+\#            | Saldot för perioden som är \# perioder efter den aktuella perioden.                   |
| /Y               | Hittills i år-saldot via aktuella perioden.                                      |
| /Y-\#            | Hittills i år-saldot genom perioden som är \# före den aktuella perioden. |
| /Y+\#            | Hittills i år-saldot genom perioden som är \# efter den aktuella perioden.  |

### <a name="book-code-modifiers"></a>Bokkodsmodifierare

Du kan begränsa en rad i en befintlig bokkod. Kolumndefinitionen måste innefatta minst en kolumn **FD** som har en bokkod.

> [!NOTE]
> Bokkodbegränsningen för en rad åsidosätter bokkodbegränsningarna i kolumndefinitionen för den raden.

### <a name="account-and-transaction-attributes"></a>konto- och transaktionsattribut

Vissa redovisningssystem stöder kontoattribut och transaktionattribut i ekonomiska data. Dessa attribut fungerar som virtuella kontosegment och kan ha mer information om kontot eller transaktionen. Denna ytterligare information kan vara konto-ID, batch-ID, postnummer eller andra attribut. Om dina attribut och redovisningssystem stöder kan du använda kontoattribut eller transaktionattribut som radmodifikatorer i raddefinitionen. Mer information om hur du åsidosätter radnformation, se avsnittet "Åsidosätt en kolumndefinition" tidigare i den här artikeln.

## <a name="specify-a-link-to-financial-dimensions-cell"></a>Ange en länk till den ekonomiska dimensioncellen
Cellen **Länka till ekonomiska dimensioner** innehåller länkar till de ekonomiska data som ska inkluderas i varje rad i en rapport. Den här cellen innehåller dimensionsvärden. Dubbelklicka på cellen **Dimensioner** för att öppna dialogrutan **Länk till ekonomiska dimensioner** .

> [!NOTE]
> Report Designer kan inte välja konton, dimensioner eller fält från Microsoft Dynamics ERP-systemet som innehåller något av följande reserverade tecken: &, \*, \[, \], {, or }. Om du vill ange information för en rad som redan finns i raddefinitionen, lägger du till informationen i cellen **Länk till ekonomiska dimensioner**. För att skapa nya rader som länkar till ekonomiska data, använd dialogrutan **Infoga rader från** för att skapa nya rader i rapportdefinitionen som länkar till de ekonomiska data. Kolumnrubriken ändras, beroende på hur kolumnen konfigureras enligt vad som visas i följande tabell.

| Länktyp som är vald       | Beskrivningen av länken ändras till den här |
|----------------------------------|----------------------------------------------------|
| Ekonomiska dimensioner             | Länk till ekonomiska dimensioner                       |
| Rapportkalkylblad                 | Ekonomisk rapportering                         |

### <a name="specify-a-dimension-or-range"></a>Ange en dimension eller ett intervall

1. Öppna den raddefinition som ska ändras i Report Designer.
2. Dubbelklicka på en cell i en kolumn av typen **Länk till ekonomiska dimensioner**.
3. I dialogrutan **Dimensioner** dubbelklickar du på en cell under dimensionsnamnet.
4. I dialogrutan för dimensionen, välj **Individuella eller intervall**.
5. I fältet **Från** anger du startdimensionen eller klickar på ![Bläddra](https://i-technet.sec.s-msft.com/dynimg/IC679490.gif "Bläddra") för att söka efter tillgängliga dimensioner. Om du vill ange ett intervall med dimensioner, anger du den avslutande dimensionen i fältet **Till** .
6. Klicka på **OK** för att stänga dialogrutan för dimensionen. Dialogrutan **Dimensioner** visar den uppdaterade dimensionen eller intervallet.
7. Klicka på **OK** för att stänga dialogrutan **Dimensioner**.

## <a name="display-zero-balance-accounts-in-a-row-definition"></a>Visa nollsaldokonton i en raddefinition
Som standard skriver rapportdesignern inte ut en rad som inte har något motsvarande saldo i ekonomiska data. Därför kan du skapa en raddefinition som omfattar alla typsegmentvärden eller alla dimensionsvärden, och sedan använda den raddefinitionen för alla dina avdelningar.

### <a name="modify-zero-balance-settings"></a>Ändra nollsaldoinställningar

1. Öppna kolumndefinitionen i Report Designer för att ändra den.
2. På fliken **Inställningar** under **Annan formatering** väljer du alternativ för den raddefinition som används i rapportdefinitionen.
3. Klicka på **Spara** på menyn **Arkiv** om du vill spara dina ändringar.

## <a name="use-wildcard-characters-and-ranges-in-a-row-definition"></a>Använd jokertecken och intervall i en raddefinition
När du anger ett typsegmentvärde i dialogrutan **Dimensioner** kan du placera ett jokertecken (? eller \*) i vilken position som helst i ett segment. Report designer hämtar alla värden för de definierade positioner utan att beakta jokertecknen. Om raddefinitionen t.ex. bara innehåller typsegmentvärden, och typsegment har fyra tecken. Genom att ange **6???** på en rad instruerar du rapportdesignern att inkludera alla konton som ett naturligt segmentvärde som börjar med 6. Om du anger **6\***, returneras samma resultat, men resultatet inkluderar också variabelbreddvärden som **60** och **600000**. Rapportdesignern ersätter varje jokertecken (?) med hela intervallet av möjliga värden, inklusive bokstäver och specialtecken. T.ex. i intervallet från **PKCS? 0** till **PKCS? 4** ersätter jokertecknet i **PKCS? 0** det lägsta värdet på teckenuppsättningen, och jokertecknet i **PKCS? 4** ersätter det högsta värdet i teckenuppsättningen.

> [!NOTE]
> Du bör undvika att använda jokertecken för start- och slutkonton i intervallet. Om du använder jokertecken i antingen startkontot eller slutkontot kan du få oväntade resultat.

### <a name="single-segment-or-single-dimension-ranges"></a>Intervall för enkelt segment eller enkel dimension

Du kan ange ett intervall med segmentvärden eller dimensionsvärden. Fördelen med att ange ett intervall är att du inte måste uppdatera raddefinitionen varje gång som en ny segmentvärde eller dimensionsvärde läggs till i ekonomiska data. Till exempel hämtar intervallet **+Konto=\[6100:6900\]** värdena från kontona 6100 till 6900 till radbeloppet. När ett intervall inkluderar ett jokertecken (?) utvärderar rapportdesignern inte intervallet baserat på tecken för tecken. I stället bestäms de lägsta och högsta värdena i intervallet och sedan inkluderas slutvärdena och alla värden mellan dem.

> [!NOTE]
> Report Designer kan inte välja konton, dimensioner eller fält från Microsoft Dynamics ERP-systemet som innehåller något av följande reserverade tecken: &, \*, \[, \], {, or }. Du kan bara lägga till ett och-tecken (&) när du automatiskt skapar definitioner med dialogrutan **Infoga rader från dimensioner**.

### <a name="multiple-segment-or-multiple-dimension-ranges"></a>Intervaller med flera segment eller flera dimensioner

När du anger ett intervall genom att använda kombinationer av flera dimensionsvärden, utförs intervalljämförelsen baserat på ..\\financial-dimensions\\dimension-by-dimension. Intervalljämförelsen kan inte göras varken baserat på tecken för tecken eller delsegment. Intervallet **+Konto=\[5000:6000\], Avdelning=\[1000:2000\], Kostnadsställe=\[00\]** innehåller bara de konton som matchar varje segment. I det här fallet måste den första dimensionen vara mellan 5000 till 6000, den andra dimensionen måste vara mellan 1000 till 2000 och den sista dimensionen måste vara 00. Till exempel **+Konto=\[5100\], Avdelning=\[1100\], Kostnadsställe=\[01\]** ingår inte i rapporten eftersom det sista segmentet ligger utanför det angivna intervallet. Om ett segmentvärde innehåller mellanslag ska det värdet omslutas med hakparentes (\[ \]). Följande värden är giltiga för ett segment med fyra tecken: **\[ 234\], \[123 \], \[1 34\]**. Dimensionsvärden ska omges av hakparenteser (\[ \]) och rapportdesignern lägger till dessa hakparenteser åt dig. Om ett intervall med flera segment eller dimensioner innehåller jokertecken (? eller \*) bestäms de lägsta och högsta värdena i hela intervallet med flera segment eller dimensioner, och sedan inkluderas slutvärdena och alla värden mellan dem. Om du har ett stort intervall, till exempel hela intervallet med konton från 40000 till 99999, ska du ange ett giltigt startkonto och slutkonto när detta är möjligt.

> [!NOTE] 
> Report Designer kan inte välja konton, dimensioner eller fält från Microsoft Dynamics ERP-systemet som innehåller något av följande reserverade tecken: &, \*, \[, \], {, or }. Du kan bara lägga till ett och-tecken (&) när du automatiskt skapar definitioner med dialogrutan **Infoga rader från dimensioner**.

## <a name="add-or-subtract-from-other-accounts-in-a-row-definition"></a>Lägga till eller dra ifrån från andra konton i en raddefinition
Om du vill lägga till penningbelopp i ett konto från penningbeloppen i annat konto kan du använda plusteckenet (+) och minustecknet (-) i cellen **Länka till ekonomiska dimensioner**. Följande tabell visar de godtagbara format för att lägga till och Subtrahera länkar till ekonomiska data.

| Operation                                                                               | Använd det här formatet                                                                                              |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Addera fullständigt kvalificerade konton.                                                       | +Division=\[000\], Konto=\[1205\], Avdelning=\[00\]+Division=\[100\], Konto=\[1205\], Avdelning=\[00\] |
| Addera två segmentvärden.                                                                 | +Konto=\[1205\]+Konto=\[1210\]                                                                           |
| Addera segmentvärden som innehåller jokertecken.                                    | +Konto=\[120?+Konto=\[11??\]                                                                             |
| Addera ett intervall med fullständigt kvalificerade konton.                                                | +Division=\[000:100\], Konto=\[1205\], Avdelning=\[00\]                                                   |
| Addera ett intervall med segmentvärden.                                                          | +Konto=\[1200:1205\]                                                                                       |
| Addera ett intervall med segmentvärden som innehåller jokertecken.                         | +Konto=\[120?:130?\]                                                                                       |
| Subtrahera ifrån ett fullständigt kvalificerat konto från ett annat fullständigt kvalificerat konto.              | +Division=\[000\], Konto=\[1205\], Avdelning=\[00\]-Division=\[100\], Konto=\[1205\], Avdelning=\[00\] |
| Subtrahera ett segmentvärde från ett annat segmentvärde.                                  | +Konto=\[1205\]-Konto=\[1210\]                                                                           |
| Subtrahera ett segmentvärde som innehåller ett jokertecken från ett annat segmentvärde. | +Konto=\[1200\]-Konto=\[11??\]                                                                           |
| Subtrahera ett intervall med fullständigt kvalificerade konton.                                           | -Division=\[000:100\], Konto=\[1200:1205\], Avdelning=\[00:01\]                                           |
| Subtrahera ett intervall med segmentvärden.                                                     | -Konto=\[1200:1205\]                                                                                       |
| Subtrahera ett intervall med segmentvärden som innehåller jokertecken.                    | -Konto=\[120?:130?\]                                                                                       |

Även om du kan ändra kontona direkt, kan du även använda dialogrutan **Dimensioner** för att använda korrekt formatering till dina ekonomiska datalänkar. Alla värden kan innehålla jokertecken (? eller \*). Report Designer kan emellertid inte välja konton, dimensioner eller fält från Microsoft Dynamics ERP-systemet som innehåller något av följande reserverade tecken: &, \*, \[, \], {, or }.

> [!NOTE]
> Om du ska subtrahera värden måste du skriva värden inom parenteser. Om du till exempel anger **450?-(4509)** visas det som **+Konto=\[4509\]-Konto=\[450?\]** och du ger instruktioner till rapportdesignern att subtrahera beloppet för kontosegment 4509 från beloppet för alla kontosegment som börjar med 450.

### <a name="add-or-subtract-accounts-from-other-accounts"></a>Addera eller subtrahera konton från andra konton

1. Öppna raddefinitionen i Report Designer för att ändra den.
2. I lämplig rad dubbelklickar u på en cell i kolumnen **Länk till ekonomiska dimensioner**.
3. Följ dessa steg i den första raden i dialogrutan **Dimensioner**:

    1. Markera alla dimensioner (standardinställning) eller klicka om du vill öppna dialogrutan **Hantera dimensionsuppsättningar** där du kan skapa, ändra, kopiera eller ta bort en uppsättning.
    2. Dubbelklicka på cellen **Operatör +/-** och välj plus- (**+**) eller minusoperatorn (**-**) som gäller för en eller flera dimensionsvärden eller uppsättningar i raden.
    3. I lämplig dimensionsvärdekolumn dubbelklickar du på cellen för att öppna dialogrutan **Dimensioner** och väljer om detta dimensionsvärde gäller för en en enskild eller ett intervall, en dimensionsvärdeuppsättning eller summeringskonton. Se avsnittet "Beskrivning av dialogrutan för dimensioner" för beskrivning av fälten i dialogrutan **Dimensioner**.
    4. Ange segmentvärden i kolumnen **Från** och kolumnen **Till** .

4. Upprepa steg 2 till och med 3 om du vill lägga till fler operationer.

> [!NOTE]
> Operatören gäller för alla dimensioner på raden.

## <a name="description-of-the-dimensions-dialog-box"></a>Beskrivning av dialogrutan Dimensioner.
I tabellen nedan beskrivs fälten i dialogrutan **Dimensioner**.

| Artikel                | Beskrivning |
|---------------------|-------------|
| Individuella eller Intervall | I fältet **Från** anger du namnet på ett konto eller klickar på knappen **Bläddra** ![Bläddra](https://i-technet.sec.s-msft.com/dynimg/IC679490.gif "Bläddra") för att bläddra till kontot. För att välja ett intervall anger du eller bläddrar efter ett värde i fältet **Till**. |
| Dimensionsvärdeuppsättning | Ange namnet på en dimensionsvärdeuppsättning i fältet **Namn**. Om du vill skapa, ändra, kopiera eller ta bort en uppsättning, klickar du på **Hantera dimensionsvärdeuppsättningar**. Fältet **Formel** fylls i med formeln från cellen **Länka till ekonomiska dimensioner** för denna dimensionsvärdeuppsättning som anges i raddefinitionen. |
| SUmmeringskonton   | I fältet **Namn** anger du eller bläddrar efter en dimension av summeringskonton. Fältet **Formel** fylls i med formeln i cellen **Länka till ekonomiska dimensioner** för detta summeringskonto i rapportdefinitionen. |

## <a name="add-dimension-value-sets-in-a-row-definition"></a>Lägg till definitionvärdeuppsättningar i en raddimension
En dimensionsvärdeuppsättning är en namngiven grupp av dimensionsvärden. En dimensionsvärdeuppsättning kan bara innehålla värden i en enda dimension, men du kan använda en dimensionsvärdeuppsättning i flera raddefinitioner, kolumndefinitioner, rapportträddefinitioner och rapportdefinitioner. Du kan också kombinera dimensionsvärdeuppsättningar i en rapportdefinition. När en ändring av dina ekonomiska data kräver att du ändrar dimensionsvärdeuppsättningen kan du uppdatera definitionen för dimensionsvärdeuppsättningen och uppdateringen tillämpas på alla områden som använder dimensionsvärdeuppsättning. Om du till exempel ofta anger ett värdeintervall till länken till dina ekonomiska data, till exempel värdena från 5100 till 5600, kan du tilldela detta intervall till en kontouppsättning med namnet Försäljning till l. När du har skapat en mängd med dimensionsvärden, kan du välja den mängden som din länk till ekonomiska data. Ett annat exempel är att om du har värdeintervallet 5100 till 5600 kopplat till Försäljning, och 4175 kopplat till Rabatter, så kan du avgöra den totala försäljningen genom att subtrahera Rabatter från Försäljning. Den här åtgärden anges som **(5100:5600)-4175**.

### <a name="create-a-set-of-dimension-values"></a>Skapa en dimensionsvärdeuppsättning.

1. I Report Designer öppnar du rad-, kolumn- eller träddefinitionen för att ändra.
2. På menyn **Redigera** klickar du opå **Hantera dimensionsvärdeuppsättningar**.
3. I dialogrutan **Hantera dimensionsvärdeuppsättningar** i fältet **Dimension** väljer du typ av dimensionsvärdeuppsättning som du vill skapa och klickar sedan på **Nytt**.
4. I dialogrutan **Nytt** anger du ett namn och en beskrivning för uppsättningen.
5. Dubbelklicka på en cell i kolumnen **Från**.
6. I dialogrutan **Konto**, välj kontonamnet i listan eller sök efter posten i fältet **Sök** . Klicka sedan på **OK**.
7. Upprepa steg 5 till 6 i kolumnen **Till** för att utforma en formel för den operatören.
8. När formeln när slutförd klickar du på **OK**.
9. Klicka på **Stäng** i dialogrutan **Hantera dimensionsgrupper**.

### <a name="update-a-set-of-dimension-values"></a>Uppdatera en mängd med dimensionsvärden

1. Öppna rad-, kolumn- eller träddefinitionen som ska ändras i Report Designer.
2. På menyn **Redigera** klickar du opå **Hantera dimensionsvärdeuppsättningar**.
3. Välj diaglogrutan **Hantera dimensionsvärdeuppsättningar** och välj dimensionstyp i fältet **Dimension**.
4. I listan väljer du den dimensionsvärdeuppsättning som ska uppdateras och klickar sedan på **Ändra**.
5. I dialogrutan **Ändra** ändrar du formelvärdena som du vill inkludera i uppsättningen.

    > [!NOTE]
    > Om du lägger till nya konton eller dimensioner, se till att du ändrar befintliga dimensionsvärdeuppsättningar om du vill föra in ändringarna.

6. Dubbelklicka på cellen och välj lämplig operatör **Från**-konto och **Till**-konto.
7. Klicka på **OK** för att stänga dialogrutan **Ändra** och spara ändringarna.

### <a name="copy-a-dimension-set"></a>Kopiera en dimensionsuppsättning

1. I Report Designer öppnar du rad-, kolumn- eller träddefinitionen för att ändra.
2. På menyn **Redigera** klickar du opå **Hantera dimensionsvärdeuppsättningar**.
3. I dialogrutan **Hantera dimensionsvärdeuppsättningar** i fältet **Dimension** väljer du dimensionstyp.
4. I listan markerar du den uppsättning som ska ändras och klickar sedan på **Välj**.
5. Ange ett nytt namn för den kopierade uppsättningen och klicka på **OK**.

### <a name="delete-a-dimension-set"></a>Ta bort en dimensionsgrupp

1. Öppna rad-, kolumn- eller träddefinitionen som ska ändras i Report Designer.
2. På menyn **Redigera** klickar du opå **Hantera dimensionsvärdeuppsättningar**.
3. Välj diaglogrutan **Hantera dimensionsvärdeuppsättningar** och välj dimensionstyp i fältet **Dimension**.
4. Markera den grupp som ska raderas och klicka på **Ta bort**. Klicka på **Ja** om du vill ta bort dimensionsvärdemängden permanent.

## <a name="additional-resources"></a>Ytterligare resurser

[Ekonomisk rapportering](financial-reporting-intro.md)
