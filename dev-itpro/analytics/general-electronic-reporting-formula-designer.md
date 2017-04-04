---
title: Formeldesigner i elektronisk rapportering
description: "Detta avsnitt avslutar hur du använder formeldesignern inom Elektronisk rapportering (ER). Om du utformar ett format för ett visst elektroniskt dokument i ER kan du använda Microsoft Excel-liknande formler för datatransformering för att uppfylla kraven för det dokumentets överensstämmelse och formatering. Olika typer av funktioner stöds - text, datum och tid, matematiska logiska information, Datatypskonverteringar och andra (domän-specifika funktionerna)."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ac8d6c064ca826cc1c2fed07578ca9ce0c66ef66
ms.lasthandoff: 03/31/2017


---

# <a name="formula-designer-in-electronic-reporting"></a>Formeldesigner i elektronisk rapportering

Detta avsnitt avslutar hur du använder formeldesignern inom Elektronisk rapportering (ER). Om du utformar ett format för ett visst elektroniskt dokument i ER kan du använda Microsoft Excel-liknande formler för datatransformering för att uppfylla kraven för det dokumentets överensstämmelse och formatering. Olika typer av funktioner stöds - text, datum och tid, matematiska logiska information, Datatypskonverteringar och andra (domän-specifika funktionerna).

<a name="formula-designer-overview"></a>Formel designer översikt
-------------------------

Elektronisk rapportering (ER) stöder formeldesignern. Därför kan du vid designtillfället konfigurera uttryck som kan användas för följande uppgifter under körning:

-   Omvandla data från en Microsoft Dynamics 365 for Operations-databas som ska användas i en ER-datamodell utformad som en datakälla för ER- format (filtrering, gruppering, datatypskonvertering osv.)
-   Formatera data som ska skickas till ett genererande elektroniskt dokument i enlighet med layouten och villkoren för ett särskilt ER-format (enligt valt språk eller kultur, kodning osv.).
-   Kontrollera processen för generering av elektroniska dokument (aktivera/inaktivera utdata för specifika element av formatet, beroende på bearbetningsdata, avbryta skapandet av dokument, kasta meddelanden för slutanvändare osv.).

Designsidan för formeln kan därför öppnas när du gör något av följande:

-   Binda datakällsartiklar till datamodellkomponenter.
-   Binda datakällsartiklar till formatkomponenter
-   Slutför underhåll av beräknade fält som en del av datakällor.
-   Definiera synlighetvillkoren för användarnas indataparametrar.
-   Utforma transformeringar för ett format.
-   Definiera aktiveringsvillkoren för formatets komponenter.
-   Definiera filnamnen för formatets FIL-komponenter.
-   Definiera villkoren för processtyrningsvalideringarna.
-   Definiera meddelandetexten för processtyrningsvalideringar.

## <a name="designing-er-formulas"></a>Utforma ER-formler
### <a name="data-binding"></a>Data bindande

ER-formeldesignern kan användas för att definiera ett uttryck som transformerar data som tagits emot från datakällor så att dessa data kan användas i datakonsumenten under körning:

-   Från Microsoft Dynamics 365 for Operations-datakällor och körtidsparametrar till en ER-datamodell.
-   Från en ER-datamodell till ett ER-format.
-   Från Microsoft Dynamics 365 for Operations-datakällor och körtidsparametrar till ett ER-dataformat.

Bilden visar hur ett uttryck av den här typen skapas. I det här exemplet returnerar uttrycket värdet i fältet **Intrastat.AmountMST** i tabellen **Intrastat** för Dynamics 365 for Operationtable, efter det att värdet har avrundats till två decimaler. [![bilden uttryck bindande](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg) i följande bild visas hur du kan använda ett uttryck av den här typen. I det här exemplet är resultatet av uttrycket avsedda fylls i den **Transaction.InvoicedAmount** komponenten i **skatt rapportmodellen** datamodellen. [![bild-uttryck-binding2](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg) vid körning utformade formeln **tur (Intrastat.AmountMST 2)**, Avrundar värdet av den **AmountMST** för varje post i den **Intrastat** tabell med två decimaler och fylla det avrundade värdet till den **Transaction.InvoicedAmount** komponenten i **skatterapportering** datamodellen.

### <a name="data-formatting"></a>Data formatering

ER-formeldesignern kan användas för att definiera uttryck som formaterar data som tagits emot från datakällor, så att dessa data kan skickas som en del av det genererade elektroniska dokumentet. Om du har en formatering som ska tillämpas som en typisk regel och återanvändas för ett format kan du kan införa den formateringen en gång i en formatkonfigurering som en namngiven transformering som har ett formateringsuttryck. Den namngivna transformeringen kan sedan länkas till flera formatkomponenter, vars utdata måste vara formaterade enligt det skapade uttrycket. Bilden nedan visar hur du skapar en transformering av den här typen. I det här exemplet tar **TrimmedString**-transformeringen inkommande data för datatypen **String** och trunkerar inledande och avslutande blanksteg när den returnerar strängvärdet. [![bilden transformeringen utformning](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg) i följande bild visas hur en omvandling av den här typen kan användas. I det här exemplet finns flera formatkomponenter som skickar text som utdata till det genererande elektroniska dokumentet i körtid och som refererar till **TrimmedString**-transformeringen efter namn. [![bilden transformeringen belastning](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg) när formatet komponenter refererar till den ** TrimmedString ** transformation (exempelvis den **partyName** komponent i bilden ovan) text som skickas för att skapa dokumentet. Texten inkluderar inte inledande eller avslutande blanksteg. Om du har en formatering som måste tillämpas separat kan du införa den formateringen som ett individuellt uttryck för en bindning av en särskild formatkomponent. Bilden visar ett uttryck av den här typen. I det här exemplet är**partyType**-formatkomponenten bunden till datakällan via ett uttryck som omvandlar inkommande data från fältet **Model.Company.RegistrationType** i datakällan till versal text och skickar texten som utdata till det elektroniska dokumentet. [![bilden bindande med formeln](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Processen flödeskontroll

ER-formeldesignern kan användas för att definiera uttryck som styr processflödet för genererande dokument. Du kan:

-   Definiera villkor som fastställer när processen för att skapa ett dokument måste stoppas.
-   Definiera uttryck som antingen skapar meddelanden till slutanvändaren om stoppade processer eller kastar körningsloggmeddelanden om den pågående processen med att skapa en rapport.
-   Definiera filnamnen på de genererande dokumenten och styr villkoren för hur de skapas.

Varje regel i processen flödeskontroll är utformad som en individuell validering. Bilden nedan visar en validering av den här typen. Här följer en förklaring av konfigureringen i det här exemplet:

-   Valideringen utvärderas när **INSTAT**-noden skapades i den genererande XML-filen.
-   Valideringen stoppar körningsprocessen och returnerar **FALSE** om listan över transaktioner är tom.
-   Valideringen returnerar ett felmeddelande som innehåller texten i etiketten SYS70894 på användarens valda språk.

[![validering av bilden](./media/picture-validation.jpg)](./media/picture-validation.jpg) ER The formeldesigner kan också användas för att ange ett filnamn för att skapa elektroniska dokument och kontrollera filen skapas. Bilden nedan visar utformningen av en styrning av ett processflöde av den här typen. Här följer en förklaring av konfigureringen i det här exemplet:

-   Listan över poster från **model.Intrastat**-datakällan delas upp i batchar som var och en innehåller upp till 1 000 poster.
-   Utdata skapar en zip-fil som innehåller en fil i XML-format för varje skapad batch.
-   Ett uttryck returnerar ett filnamn för genererande elektroniska dokument genom att konkatenera filnamnet och filsuffixet. För den andra batchen och alla efterföljande batchar innehåller filnamnet batchens ID som ett suffix.
-   Ett uttryck möjliggör (genom att returnera **TRUE**) processen för att skapa en fil för batchar som innehåller minst en post.

[![filen bildkontroll](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Grundläggande syntax

ER-uttryck kan innehålla några eller flera av följande element:

-   Konstanter
-   Operatorer
-   Referenser
-   Sökvägar
-   Funktioner

#### <a name="constants"></a>Konstanter

Du kan använda text och numeriska konstanter (värden som inte är beräknade) för att utforma uttryck. Till exempel uttrycket ** värde ("100") + 20 ** använder numerisk konstant 20 och konstant "100" strängen och returnerar det numeriska värdet **120**. ER-formeldesignern stöder escape-sekvenser, vilket innebär att du kan definiera den del av strängen i uttrycket som ska hanteras på ett annat sätt. Till exempel returnerar uttrycket **"Leo Tolstoy" "Krig och fred" "Volym 1"** textsträngen **Leo Tolstoy "Krig och fred" Volym 1**.

#### <a name="operators"></a>Operatorer

Följande tabell visar de aritmetiska operatorer du kan använda för att utföra grundläggande matematiska operationer såsom addition, subtraktion, division och multiplikation.

| Operatör | Betydelse              | Exempel |
|----------|----------------------|---------|
| +        | Tillägg             | 1 + 2     |
| -        | Subtraktionsnegering | 5 – 2 –1  |
| \*       | Multiplikation       | 7\*8    |
| /        | Indelning             | 9/3     |

Följande tabell visar jämförelseoperatorerna som stöds och som du kan använda för att jämföra två värden.

| Operatör | Betydelse                  | Exempel    |
|----------|--------------------------|------------|
| =        | Lika                    | X = Y        |
| &gt;     | Större än             | X&gt;Y     |
| &lt;     | Mindre än                | X&lt;Y     |
| &gt;=    | Större än eller lika med | X&gt;=Y    |
| &lt;=    | Mindre än eller lika med    | X&lt;=Y    |
| &lt;&gt; | Inte lika med             | X&lt;&gt;Y |

Du kan dessutom använda et-tecknet (&) som en textkonkateneringsoperator för att sammanfoga (konkatenera) en eller flera textsträngar till en enda text.

| Operatör | Betydelse     | Exempel                                        |
|----------|-------------|------------------------------------------------|
| &        | Sammanfoga | "Det finns inget att skriva ut" & ": " & "inga poster hittades" |

#### <a name="operator-precedence"></a>Operatorprioritet

Ordningen i vilken delarna i ett sammansatt uttryck utvärderas är viktig. Exempelvis resultatet av uttrycket ** 1 + 4 / 2 ** beror på om Additionen eller åtgärden division utförs först. Du kan använda parenteser för att explicit definiera hur ett uttryck utvärderas. Om du till exempel vill ange att additionsoperationen ska utföras först kan du ändra det föregående uttrycket till **(1 + 4)/2**. Om ordningen för operationer som ska utföras i ett uttryck inte anges explicit baseras ordningen på standardprioriteten som tilldelats de operatorer som stöds. Följande tabell visar operatorerna och den prioritet som tilldelats respektive operator. Operatorer som har högre prioritet (till exempel 7) utvärderas före operatorer med lägre prioritet (exempelvis 1).

| Prioritet | Operatorer      | Syntax                                                   |
|------------|----------------|----------------------------------------------------------|
| 7          | Gruppering       | ( … )                                                    |
| 6          | Medlemsåtkomst  | … . …                                                    |
| 5          | Funktionsanrop  | … ( … )                                                  |
| 4          | Multiplikation | … \* … … / …                                             |
| 3          | Additiv       | … + … … - …                                              |
| 2          | Jämförelse     | … &lt; … … &lt;= … … =&gt; … … &gt; … … = … … &lt;&gt; … |
| 1          | Separation     | … , …                                                    |

Operatorer på samma rad har samma prioritet. Om ett uttryck omfattar fler än en av dessa operatorer utvärderas uttrycket från vänster till höger. Till exempel uttrycket **1 + 6 / 2 \*3 &gt;5** returnerar **SANT**. Vi rekommenderar att du använder parenteser om du explicit vill ange önskad ordning för utvärdering av uttryck för att göra uttrycken enklare att läsa och underhålla.

#### <a name="references"></a>Referenser

Alla datakällor för den aktuella ER-komponenten (en modell eller ett format) som är tillgängliga under utformningen av ett uttryck kan användas som namngivna referenser. Till exempel innehåller den aktuella ER-datamodellen datakällan **ReportingDate** som returnerar ett värde av datatypen **DATETIME**. Om du vill formatera korrekt värde i dokumentet för att skapa, du kan referera till datakällan i uttrycket på följande sätt: **DATETIMEFORMAT (ReportingDate, "dd-MM-ÅÅÅÅ")** alla tecken som inte representerar en bokstav i alfabetet i en refererande datakälla måste föregås av en apostrof ('). Om namnet på en refererande datakälla innehåller minst ett tecken som inte representerar en bokstav i alfabetet (t.ex, skiljetecken eller andra symboler skrivna), måste vilket omges med enkla citattecken. Nedan följer några exempel:

-   Det måste finnas en referens till datakällan **Dagens datum och tid** i ett ER-uttryck enligt följande **'Dagens datum och tid'**.
-   Det måste finnas en referens till metoden **name()** för datakällan **Customers** i ett ER-uttryck enligt följande: **Customers.'name()'**

#### <a name="path"></a>Sökväg

När ett uttryck refererar till en strukturerad datakälla kan du använda sökvägsdefinitionen för att välja ett specifikt primitivt element i den datakällan. En punkt (.) används för separera enskilda element i en strukturerad datakälla. Till exempel innehåller den aktuella ER-datamodellen datakällan **InvoiceTransactions** som returnerar en lista över poster. Poststrukturen ** InvoiceTransactions** innehåller fälten **AmountDebit** och **AmountCredit**, som returnerar numeriska värden. Ett uttryck för att beräkna det fakturerade beloppet kan därför utformas på följande sätt: **InvoiceTransactions.AmountDebit – InvoiceTransactions.AmountCredit**.

#### <a name="functions"></a>Funktioner

Nästa avsnitt innehåller beskrivningar av de funktioner som kan användas i ER-uttryck. Alla datakällor i uttryckets sammanhang (aktuell ER-datamodell eller aktuellt ER-format) och även andra konstanter kan användas som parametrar för anropsfunktioner i enlighet med listan över argument för anropsfunktionen. Till exempel innehåller den aktuella ER-datamodellen datakällan **InvoiceTransactions** som returnerar en lista över poster. Poststrukturen ** InvoiceTransactions** innehåller fälten **AmountDebit** och **AmountCredit**, som returnerar numeriska värden. Ett uttryck för att beräkna det fakturerade beloppet kan utformas på följande sätt med hjälp av den inbyggda ER-avrundningsfunktionen: **ROUND (InvoiceTransactions.AmountDebit – InvoiceTransactions.AmountCredit, 2)**.

## <a name="supported-functions"></a>Funktioner som stöds
I följande tabeller finns beskrivningar av datamanipuleringsfunktioner kan användas för att designa ER-datamodeller och ER-rapporter. Listan med funktioner är inte fast och kan utökas av utvecklare. Om du vill se listan över vilka funktioner du kan använda ska du gå till funktionsfönstret i ER-formeldesignern.

### <a name="date-and-time-functions"></a>Datum- och tidsfunktioner

| Funktion                                   | Beskrivning                                                                                                                                                                                                                                                                                                                                                      | Exempel                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ADDDAYS (datetime, days)                   | Lägger till det angivna antalet dagar till det definierade datetime-värdet.                                                                                                                                                                                                                                                                                                | **ADDDAYS (NOW(), 7)** returnerar datum och tid sju dagar framöver.                                                                                                                                                                                                                            |
| DATETODATETIME (date)                      | Konverterar det definierade datumvärdet till ett datetime-värde.                                                                                                                                                                                                                                                                                                            | **DATETODATETIME (CompInfo. "getCurrentDate()')** returnerar aktuellt Dynamics 365 för operationer sessionsdatum, 12/24/2015 som **2015/24/12 12:00:00: 00**. I det här exemplet är **CompInfo** en ER-datakälla av typen **Dynamik 365 for Operations/Table** som refererar till CompanyInfo-tabellen. |
| NOW ()                                     | Returnerar aktuellt datum och aktuell tid för Dynamics 365 for Operations-servern som ett datetime-värde.                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                       |
| TODAY ()                                   | Returnera aktuellt datum för Dynamics 365 for Operations-programservern som ett datumvärde.                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                       |
| NULLDATE ()                                | Returnerar date-värdet **null**.                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                       |
| NULLDATETIME ()                            | Returnerar datetime-värdet **null**.                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                       |
| DATETIMEFORMAT (datetime, format)          | Konverterar det definierade datetime-värdet till en sträng i det definierade formatet. (Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).)                                                                        | **DATETIMEFORMAT (NOW(), "åååå-mm-dd")** returnerar det aktuella Dynamics 365 for Operations-programserverdatumet, 2015-12-24, som **"2015-12-24"**enligt det definierade anpassade formatet.                                                                                                          |
| DATETIMEFORMAT (datetime, format, culture) | Konverterar det definierade datetime-värdet till en sträng i det definierade formatet och [kulturen](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), "s", "sv")** returnerar det aktuella datumet för Dynamics 365 for Operations-programservern, 2015-12-24, som **"2015-12-24"** enligt den valda svenska kulturen.                                                                                                             |
| SESSIONTODAY ()                            | Returnerar aktuellt datum för Dynamics 365 for Operations-session som ett datumvärde.                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                       |
| SESSIONNOW ()                              | Returnerar aktuellt datum och tid för Dynamics 365 for Operations-session som ett datetime-värde.                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                       |
| DATEFORMAT (datum, format)                  | Returnerar en strängrepresentation av datumet med ett angivet format.                                                                                                                                                                                                                                                                                                    | **DATEFORMAT (SESSIONTODAY (), "åååå-mm-dd")** returnerar det aktuella Dynamics 365 for Operations-sessionsdatumet, 2015-12-24, som "**2015-12-24"**" enligt det definierade anpassade formatet.                                                                                                                      |
| DATEFORMAT (datum, format, kultur)         | Konverterar det angivna datumvärdet till en sträng i det definierade formatet och den definierade [kulturen](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).)     | **DATETIMEFORMAT (SESSIONNOW (), "s", "sv")** returnerar det aktuella sessionsdatumet för Dynamics 365 for Operations, 2015-12-24, som **"2015-12-24"** enligt den valda svenska kulturen.                                                                                                                       |

### <a name="list-functions"></a>Lista över funktioner

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktion</th>
<th>beskrivning</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SPLIT (input, length)</td>
<td>Delar upp den definierade indatasträngen i delsträngar som var och en är av den definierade längden. Returnerar resultatet som en ny lista.</td>
<td><strong>Dela (&quot;abcd&quot;, 3)</strong> returnerar en ny lista som består av två poster som har ett <strong>sträng</strong> fält. Fält i den första posten innehåller text <strong>&quot;abc&quot;</strong>, och fältet i den andra posten innehåller texten <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr class="even">
<td>SPLITLIST (list, number)</td>
<td>Delar upp den angivna listan i batchar som var och en innehåller det definierade antalet poster. Returnerar resultatet som en ny lista med batchar som innehåller följande element:
<ul>
<li>Batchar som vanliga listor (<strong>Value </strong>component)</li>
<li>Det aktuella batchnumret (<strong>BatchNumber </strong>component)</li>
</ul></td>
<td>I följande exempel skapas datakällan <strong>Lines</strong> som en postlista med tre poster som delas upp i batchar som var och en innehåller högst två poster. <a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>Detta visar layouten designade format där bindningar till den <strong>rader</strong> datakälla skapas för att generera utdata i XML-format som visar enskilda noder för varje grupp och poster i den. <a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>Följande beror på utformade formateringen. <a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LIST (record 1 [, record 2, ...])</td>
<td>Returnerar en ny lista som skapas från de definierade argumenten.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> returnerar en tom post där fältlistan innehåller alla fält i postlistorna <strong>MainData</strong> och <strong>OtherData</strong>.</td>
</tr>
<tr class="even">
<td>LISTJOIN (list 1, list 2, ...)</td>
<td>Returnerar en konkatenerad lista som skapas från listor med definierade argument.</td>
<td><strong>LISTJOIN (delar (&quot;abc&quot;, 1), dela upp (&quot;def&quot;, 1))</strong> att returnera sex poster om ett i den <strong>sträng</strong> datatyp som innehåller samma bokstäver.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (list)</td>
<td>Returnerar <strong>TRUE</strong> om den definierade listan inte innehåller några element. Annars returneras <strong>FALSE</strong>.</td>
<td></td>
</tr>
<tr class="even">
<td>EMPTYLIST (list)</td>
<td>Returnerar en tom lista genom att använda den definierade en lista som källa för liststrukturen.</td>
<td><strong>EMPTYLIST (delar (&quot;abc&quot;, 1))</strong> returnerar en ny tom lista som har samma struktur som den lista som returneras av <strong>dela</strong> funktion.</td>
</tr>
<tr class="odd">
<td>FIRST (list)</td>
<td>Returnerar den första posten i den definierade listan, om posten inte är tom. I annat fall kastas ett undantag.</td>
<td></td>
</tr>
<tr class="even">
<td>FIRSTORNULL (list)</td>
<td>Returnerar den första posten i den definierade listan, om posten inte är tom. I annat fall returneras en <strong>null</strong>-post.</td>
<td></td>
</tr>
<tr class="odd">
<td>LISTOFFIRSTITEM (list)</td>
<td>Returnerar en lista som endast innehåller det första objektet i den definierade listan.</td>
<td></td>
</tr>
<tr class="even">
<td>ALLITEMS (path)</td>
<td>Returnerar en ny platt lista som representerar alla artiklar som matchar den definierade sökvägen. Sökvägen måste anges som en giltig datakällssökväg till ett datakällslement av datatypen ”postlista”. Denna sökväg till sträng, datum och andra dataelement bör generera ett fel vid designtidpunkten i ER-uttrycksgeneratorn.</td>
<td>Om du anger <strong>delar (&quot;abcdef&quot;, 2)</strong> som datakälla (DS) <strong>COUNT (ALLITEMS (DS. Värde))</strong> returnerar <strong>3</strong>.</td>
</tr>
<tr class="odd">
<td>ORDERBY (list [, expression 1, expression 2, …])</td>
<td>Returnerar den definierade listan, sorterade efter de definierade argumenten som kan definieras som uttryck.</td>
<td>När <strong>Vendor</strong> konfigureras som en ER-datakälla som refererar till tabellen VendTable, <strong>ORDERBY (Vendors, Vendors.'name()')</strong> returneras en lista med leverantörerna sorterade efter namn i stigande ordning.</td>
</tr>
<tr class="even">
<td>REVERSE (list)</td>
<td>Returnerar den definierade listan i omvänd sorteringsordning.</td>
<td>När <strong>Vendor</strong> konfigureras som en ER-datakälla som refererar till tabellen VendTable, <strong>REVERSE (ORDERBY (Vendors, Vendors.'name()')) )</strong> returneras en lista med leverantörerna sorterade efter namn i fallande ordning.</td>
</tr>
<tr class="odd">
<td>WHERE (list, condition)</td>
<td>Returnerar den definierad listan, som är filtrerad enligt det definierade kriteriet. Till skillnad från funktionen <strong>FILTER</strong> tillämpas angivet villkor på listan i minnet.</td>
<td>När <strong>leverantör</strong> är konfigurerad som en datakälla för ER som refererar till tabellen VendTable <strong>där (leverantörer, Vendors.VendGroup = &quot;40&quot;)</strong> returnerar en lista med leverantörer som hör till 40 leverantörsgruppen.</td>
</tr>
<tr class="even">
<td>ENUMERATE (list)</td>
<td>Returnerar en ny lista som består av fasta poster i den definierade listan och som visar följande element:
<ul>
<li>Definierade listposter som vanliga listor (<strong>Value </strong>component)</li>
<li>Den aktuella postens index (<strong>Number </strong>component)</li>
</ul></td>
<td>I följande exempel är datakällan <strong>Enumerated</strong> skapad som en fast lista över leverantörsposter från datakällan <strong>Vendors</strong>, som refererar till tabellen <strong>VendTable</strong>. <a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>Här är formatet där databindningar har skapats för att generera utdata i XML-format som visar enskilda leverantörer som fasta noder. <a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>Detta beror på att köra designade format. <a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>COUNT (list)</td>
<td>Returnerar det antalet poster i den definierade i listan, om listan inte är tom. Annars returneras <strong>0</strong> (noll).</td>
<td><strong>Antal (dela (&quot;abcd&quot;, 3))</strong> returnerar <strong>2</strong>, eftersom de <strong>dela</strong> funktion skapar en lista som består av två poster.</td>
</tr>
<tr class="even">
<td>LISTOFFIELDS (sökväg)</td>
<td>Returnerar en postlist som har skapats av ett argument tillhörande en av följande typer:
<ul>
<li>Uppräkning för modell</li>
<li>Formatuppräkning</li>
<li>Behållare</li>
</ul>
Den skapade listan består av poster med följande fält:
<ul>
<li>Namn</li>
<li>Etikett</li>
<li>beskrivning</li>
</ul>
I samband med körning returnerar fälten Label och Description värden baserade på formatets språkinställningar.</td>
<td>I följande exempel visar uppräkningen som introducerats i datamodellen. <a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="GER LISTOFFIELDS function - model enumeration" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>Följande exempel visar:
<ul>
<li>Modelluppräkning har infogats i en rapport som en datakälla.</li>
<li>ER-uttryck utformat att använda modelluppräkning som en parameter för denna funktion.</li>
<li>Datakällan för den typ av postlista som infogats i en rapport genom det skapade ER-uttrycket.</li>
</ul><ph id="t1">
< en href="./media/ger-listoffields-function-in-format-expression.png" ></ph><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="GER LISTOFFIELDS function - in format expression" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a> i följande exempel visas ER formaterar element som är kopplade till en datakälla av typen post lista som skapats med funktionen LISTOFFIELDS. <a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="GER LISTOFFIELDS function - format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>Detta är resultatet av körningen designade format. <a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="GER LISTOFFIELDS function - format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a><strong>Obs!:</strong> fylls översatt text för etiketterna och beskrivningar till ER formatet i enlighet med språkinställningarna för den överordnade filen och MAPPEN formaterar element.</td>
</tr>
<tr class="odd">
<td>STRINGJOIN (lista, fältnamn, avgränsare)</td>
<td>Returnerar en sträng bestående av sammanfogade värden från ett fält i en lista som separerats med en vald avgränsare.</td>
<td>Om du anger SPLIT(“abc” , 1) som en datakälla DS, kommer uttrycket STRINGJOIN (DS, DS.Value, “:”) att returnera “a:b:c”</td>
</tr>
<tr class="even">
<td>SPLITLISTBYLIMIT (lista, gränsvärde, gränskälla)</td>
<td>Delar angiven lista i en ny lista bestående av underlistor och returnerar resultatet i form av innehåll i en postlista. Parametern för gränsvärde anger värdet på den gräns som delar ursprungslistan. Gränskälleparametern anger det steg med vilket totalsumman höjs. Gränsen tillämpas inte på en enskild artikel i angiven lista när gränskällan överskrider angiven gräns.</td>
<td>I följande exempel visas exempelformatet med datakällor. <a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="GER SPLITLISTBYLIMIT - format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="GER SPLITLISTBYLIMIT - datasources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>Detta är resultatet format utförandet som visar en plan lista över artiklar med artikelkod. <a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="GER SPLITLISTBYLIMIT - output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>i följande exempel visas samma format som justerades för att visa listan med artiklar i systemet i batchar när ett parti skall omfatta varor med en totalvikt som inte får överstiga gränsen på 9. <a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="GER SPLITLISTBYLIMIT - format 1" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="GER SPLITLISTBYLIMIT - datasources 1" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>Detta är resultatet av körningen justerade format. <a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="GER SPLITLISTBYLIMIT - output 1" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a><strong>Anmärkning:</strong> gränsen tillämpas inte på det sista objektet i listan ursprung som överstiger värdet (11) av sin gräns (vikt) definierade gränsen (9). Använd antingen funktionen <strong>WHERE</strong> eller uttrycket <strong>Enabled</strong> för respektive formatelement för att ignorera (hoppa över) underlistor i samband med rapportgenerering (vid behov).</td>
</tr>
<tr class="odd">
<td>FILTER (list, villkor)</td>
<td>Returnerar den angivna listan filtrerad för det angivna skicket genom att ändra frågan. Till skillnad från funktionen <strong>WHERE</strong> tillämpas det angivna villkoret i databasnivån till alla ER-datakällor av typen registerpost.</td>
<td>FILTER (leverantörer, Vendors.VendGroup = &quot;40&quot;) att returnera endast leverantörer som tillhör grupp leverantörernas "40" när <strong>leverantör</strong> konfigureras som datakälla för ER som refererar till den <strong>VendTable</strong> register</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Logiska funktioner

| Funktion                                                                                | beskrivning                                                                                                                                                                                                                                                                     | Exempel                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| LÅDA (uttryck, alternativ 1 leda 1 \[, val 2, leda 2\] ... \[, standard resultatet\]) | Utvärderar det definierade uttryckets värde mot de definierade alternativa alternativen. Returnerar resultatet av alternativet som är lika med värdet av uttrycket. I annat fall returneras det alternativt angivna standardresultatet (den senaste parameter som inte föregås av ett alternativ). | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")** returnerar strängen **"WINTER"** om det aktuella Dynamics 365 for Operations-sessionsdatumet är mellan oktober och december. Annars returneras en tom sträng. |
| IF (condition, value 1, value 2)                                                        | Returnerar det definierade värdet 1, när det definierade kriteriet uppfylls. Annars returnera värdet 2. Om värdet 1 och värdet 2 poster eller postlistor, får resultatet endast fält som finns i båda listorna.                                                                     | **IF (1=2, "condition is met", "condition is not met")** returnerar strängen **"villkoret är inte uppfyllt"**.                                                                                                                                                      |
| NOT (condition)                                                                         | Returnerar det omvända logiska värdet för det definierade kriteriet.                                                                                                                                                                                                                   | **NOT (TRUE)** returnerar **FALSE**.                                                                                                                                                                                                                            |
| OCH (villkor 1\[, villkor 2... \])                                                 | Returnerar **TRUE** om *alla* definierade kriterier är sanna. Annars returneras **FALSE**.                                                                                                                                                                                            | **AND (1=1, "a"="a")** returnerar **TRUE**. **AND (1=2, "a"="a")** returnerar **FALSE**.                                                                                                                                                                           |
| ELLER (villkor 1\[, villkor 2... \])                                                  | Returnerar **FALSE** om *alla* definierade kriterier är falska. Returnerar **TRUE** om *något* av de definierade kriterierna är sant.                                                                                                                                                                 | **OR (1=2, "a"="a")** returnerar **TRUE**.                                                                                                                                                                                                                      |

### <a name="mathematical-functions"></a>Matematiska funktioner

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktion</th>
<th>Beskrivning</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ABS (number)</td>
<td>Returnerar absolutvärdet för det definierade talet (talet utan dess tecken).</td>
<td><strong>ABS (-1)</strong> returnerar <strong>1</strong>.</td>
</tr>
<tr class="even">
<td>POWER (number, power)</td>
<td>Returnerar resultatet av en ökning av det definierade positiva talet till den definierade kraften.</td>
<td><strong>POWER (10, 2)</strong> returnerar <strong>100</strong>.</td>
</tr>
<tr class="odd">
<td>NUMBERVALUE (string, decimal separator, digit grouping separator)</td>
<td>Konverterar den definierade strängen till ett tal. Den angivna symbolen används för att åtskilja heltal och decimaler i ett decimaltal. Definierad tusentalsavgränsare används också.</td>
<td><strong>NUMBERVALUE (&quot;1-234,56&quot;, &quot;,&quot;, &quot;&quot;)</strong> returnerar värdet <strong>skriver 1234,56</strong>.</td>
</tr>
<tr class="even">
<td>VALUE (string)</td>
<td>Konverterar den definierade strängen till ett tal. Kommatecken och punkter (.) betraktas som decimalavgränsare och bindestreck (-) används som ett negativt tecken. Kasta ett undantag om andra icke-numeriska tecken upptäcks i den definierade strängen.</td>
<td><strong>VÄRDE (&quot;1-234,56&quot;)</strong> ett undantag.</td>
</tr>
<tr class="odd">
<td>ROUND (number, decimals)</td>
<td>Returnerar det definierade talet avrundat till det angivna antalet decimaler:
<ul>
<li>Om det definierade decimalvärdet är större än 0 (noll) avrundas det definierade talet till det angivna antalet decimaler.</li>
<li>Om det definierade decimalvärdet är 0 (noll) avrundas det definierade talet till närmaste heltal.</li>
<li>Om det definierade decimalvärdet är mindre än 0 (noll) avrundas det definierade talet till vänster om decimaltecknet.</li>
</ul></td>
<td><strong>ROUND (1200.767, 2)</strong> avrundar till två decimaler och returnerar <strong>1200.77</strong>. <strong>ROUND (1200.767, -3)</strong> avrundar till närmaste multipel av 1 000 och returnerar <strong>1000</strong>.</td>
</tr>
<tr class="even">
<td>ROUNDDOWN (number, decimals)</td>
<td>Returnerar det definierade talet avrundat nedåt (mot noll) till det angivna antalet decimaler. <strong>Obs!</strong> Den här funktionen fungerar som <strong>ROUND</strong>, men avrundar alltid det definierade talet nedåt.</td>
<td><strong>ROUNDDOWN (1200.767, 2)</strong> avrundar nedåt till två decimaler och returnerar <strong>1200.76</strong>. <strong>ROUNDDOWN (1700.767, -3)</strong> avrundar nedåt till närmaste multipel av 1 000 och returnerar <strong>1000</strong>.</td>
</tr>
<tr class="odd">
<td>ROUNDUP (number, decimals)</td>
<td>Returnerar det definierade talet avrundat uppåt (från noll) till det angivna antalet decimaler. <strong>Obs!</strong> Den här funktionen fungerar som <strong>ROUND</strong>, men avrundar alltid det definierade antalet uppåt.</td>
<td><strong>ROUNDUP (1200.763, 2)</strong> avrundar uppåt till två decimaler och returnerar <strong>1200.77</strong>. <strong>ROUNDUP (1200.767, -3)</strong> avrundar uppåt till närmaste multipel av 1 000 och returnerar <strong>2000</strong>.</td>
</tr>
</tbody>
</table>

### <a name="record-functions"></a>Inspelningsfunktioner

| Funktion             | Beskrivning                                                                                                                                                                                                                                     | Exempel                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| NULLCONTAINER (list) | Returnerar en **null**-post som har samma struktur som den definierade postlistan eller posten. **Obs! **Den här funktionen är föråldrad. Använd **EMPTYRECORD** i stället.                                                                                  | **NULLCONTAINER (SPLIT ("abc", 1))** returnerar en ny tom post som har samma struktur som listan som returneras från **SPLIT**-funktionen. |
| EMPTYRECORD (record) | Returnerar en **null**-post som har samma struktur som den definierade postlistan eller posten. **Anmärkning:** A **null** post är en post där alla fält som innehåller ett tomt värde (**0**\[noll\] för tal, en tom sträng för strängar, osv). | **EMPTYRECORD (SPLIT ("abc", 1))** returnerar en ny tom post som har samma struktur som listan som returneras från **SPLIT**-funktionen.   |

### <a name="text-functions"></a>Textfunktioner

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktion</th>
<th>Beskrivning</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>UPPER (string)</td>
<td>Returnerar den definierade strängen konverterad till versaler.</td>
<td><strong>ÖVRE (&quot;provet&quot;)</strong> returnerar <strong>&quot;provet&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LOWER (string)</td>
<td>Returnerar den definierade strängen konverterad till gemener.</td>
<td><strong>NEDRE (&quot;provet&quot;)</strong> returnerar <strong>&quot;provet&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>LEFT (string, number of characters)</td>
<td>Returnerar det definierade antalet tecken från början av den definierade strängen.</td>
<td><strong>VÄNSTER (&quot;provet&quot;, 3)</strong> returnerar <strong>&quot;Sam&quot;</strong>.</td>
</tr>
<tr class="even">
<td>RIGHT (string, number of characters)</td>
<td>Returnerar det definierade antalet tecken från slutet av den definierade strängen.</td>
<td><strong>HÖGER (&quot;provet&quot;, 3)</strong> returnerar <strong>&quot;xempel&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>MID (string, starting position, number of characters)</td>
<td>Returnerar det definierade antalet tecken från den definierade strängen, med start från den definierade positionen.</td>
<td><strong>MID (&quot;provet&quot;, 2, 3)</strong> returnerar <strong>&quot;och&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LEN (string)</td>
<td>Returnerar antalet tecken i den definierade strängen.</td>
<td><strong>LÄNGD (&quot;provet&quot;)</strong> returnerar <strong>6</strong>.</td>
</tr>
<tr class="odd">
<td>CHAR (number)</td>
<td>Returnerar teckensträngen som har en referens till det definierade Unicode-numret.</td>
<td><strong>TECKEN (255)</strong> returnerar <strong>&quot;ÿ&quot;</strong>. <strong>Obs!</strong> Den returnerade vilar på den kodning som har valts i det överordnade filformatelementet. Listan över de kodningar som stöds finns i ämnet <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Encoding class</a>.</td>
</tr>
<tr class="even">
<td>CONCATENATE (string 1 [, string 2, …])</td>
<td>Returnera alla definierade textsträngar som är konkatenerade till en sträng.</td>
<td><strong>SAMMANFOGA (&quot;abc&quot;, &quot;def&quot;)</strong> returnerar <strong>&quot;abcdef&quot;</strong>. <strong>Anmärkning:</strong> uttrycket <strong>&quot;abc&quot;&amp;&quot;def&quot;</strong> returnerar också <strong>&quot;abcdef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TRANSLATE (string, pattern, replacement)</td>
<td>Returnerar den definierade strängen i vilken alla förekomster av tecknen i den definierade mönstersträngen ersätts av tecknen på motsvarande position i den definierade utbytessträngen.</td>
<td><strong>ÖVERSÄTT (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> ersätter mönstret <strong>&quot;cd&quot;</strong> med strängen <strong>&quot;GH&quot;</strong> och returnerar <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="even">
<td>REPLACE (string, pattern, replacement, regular expression flag)</td>
<td>När ett definierat reguljärt uttrycks flagga har värdet <strong>true</strong> returneras den definierade strängen som har ändrats genom att ett reguljärt uttryck som definierats som ett mönsterargument för den här funktionen tillämpas. Uttrycket används för att hitta tecken som måste ersättas. Tecknen i det definierade utbytesargumentet används för att ersätta tecken som hittas. Om flaggan för det definierade reguljära uttrycket har värdet <strong>false</strong>uppför sig den här funktionen på samma sätt som <strong>TRANSLATE</strong>.</td>
<td>  <strong>Ersätt (&quot;+1 923 456 4971&quot;, &quot;[^ 0-9]&quot;, &quot;&quot;, SANT)</strong> används ett reguljärt uttryck som tar bort alla icke-numeriska symboler och returnerar <strong>&quot;19234564971&quot;</strong>. <strong>Ersätt (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, FALSKT)</strong> ersätter mönstret <strong>&quot;cd&quot;</strong> med strängen <strong>&quot;GH&quot;</strong> och returnerar <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TEXT (input)</td>
<td>Returnera den specificerade indatan, som konverteras till en textsträng och formateras i enlighet med serverns lokala inställningar för den aktuella instansen av Dynamics 365 for Operations. För värden av typen <strong>real</strong> är strängkonverteringen begränsad till två decimaler.</td>
<td>Om Dynamics 365 för operationer instans server språk definieras som <strong>engelska</strong>, <strong>TEXT (nu ())</strong> returnerar aktuellt Dynamics 365 för operationer sessionsdatum, 12/17/2015 som strängen <strong>&quot;12/17/2015 07:59:23 kl&quot;</strong>. <strong>TEXT (1/3)</strong> returnerar <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMAT (string 1, string 2[, string 3, ...])</td>
<td>Returnerar den definierade strängen som har formaterats så att alla förekomster av <strong>%N</strong> har ersatts med <em>n</em>:te argumentet. Argumenten är strängar. Om ett argument inte anges för en parameter parametern returneras som <strong>&quot;%N&quot;</strong> i strängen. För värden av typen <strong>real</strong> är strängkonverteringen begränsad till två decimaler.</td>
<td>I det här exemplet returnerar datakällan <strong>PaymentModel</strong> listan över kundposter via komponenten <strong>Customer</strong> och bearbetar datumvärdet via fältet <strong>ProcessingDate</strong>. <a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>I formatet ER har utformats för att generera en elektronisk fil för valda kunder <strong>PaymentModel</strong> markeras som datakälla och kontrollerar processflödet. Ett undantag kastas för slutanvändare när en vald kund stoppas för det datum då rapporten bearbetas. Formeln, som utformats för denna typ av bearbetningsstyrning, kan endast använda följande resurser:
<ul>
<li>Dynamics 365 for Operations-etikett SYS70894, som har följande text:
<ul>
<li><strong>För engelska språket:</strong>&quot;inget att skriva ut&quot;</li>
<li><strong>För DE språk:</strong>&quot;drucken Nichts zu&quot;</li>
</ul></li>
<li>Dynamics 365 for Operations-etikett SYS18389, som har följande text:
<ul>
<li><strong>För engelska språket:</strong>&quot;kund %1 har spärrats för %2.&quot;</li>
<li><strong>För DE språk:</strong>&quot;gesperrt Debitor '%1' wird für %2.&quot;</li>
</ul></li>
</ul>
Formeln kan utformas: FORMAT (sammanfoga (@&quot;SYS70894&quot;,&quot;. &quot;@&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (modell. ProcessingDate, &quot;d&quot;)) om en rapport har bearbetats för den <strong>Litware Retail kund</strong> på 17 December 2015 i den <strong>engelska</strong> kultur och <strong>engelska</strong> språk formeln returnerar följande texten som visas som ett undantaget visas för slutanvändaren: &quot;inget att skriva ut. Kunden Litware Retail har spärrats för 12/17/2015.&quot; Om samma rapport bearbetas för den<strong> Litware Retail kund</strong> på 17 December 2015 i den <strong>DE</strong> kultur och <strong>DE</strong> språk, returnerar följande formel följande text som använder ett annat datumformat: &quot;drucken Nichts zu. Debitor 'Litware butik' wird für 17.12.2015 gesperrt.&quot; <strong>Obs!</strong>Följande syntax tillämpas i ER-formler för etiketter:
<ul>
<li><strong>Om etiketter från Dynamics 365 för operationsresurser:</strong> <strong>@&quot;X&quot;</strong>, där X är etikett-ID i programobjektträdet (AOT)</li>
<li><strong>För etiketter som ingår i ER konfigurationer:</strong> <strong>@&quot;ER_LABEL:X&quot;</strong>, där X är i ER konfigurationen etikett-ID</li>
</ul></td>
</tr>
<tr class="odd">
<td>NUMBERFORMAT (number, format)</td>
<td>Returnerar strängen som representerar det definierade talet i det angivna formatet. (Information om format som stöds finns i <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">standard</a> och <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">anpassade</a>.) Funktionen körs i kontexten anger kulturen som används för att formatera tal.</td>
<td>För EN-US kultur, <strong>NUMBERFORMAT (0,45 &quot;p&quot;)</strong> returnerar <strong>&quot;45,00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> returnerar <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (nummer, språk, valuta, skriv ut flagga för valutanamn, decimaler)</td>
<td>Returnerar angivet nummer (konverterat) till textsträngar på angivet språk.. Språkkoden är valfri: när den definieras som en tom sträng kommer språkkoden för den löpande kontexten (som definierats för en genererande mapp eller fil) att användas i stället. Valutakoden är valfri. När den definieras som en tom sträng, används företagsvalutan. Notera att parametern <strong>Print currency name</strong> och parametern <strong>Decimal points</strong> endast analyseras för följande språkkoder: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong>, <strong>RU</strong>. Notera att parametern <strong>Print currency name</strong> endast analyseras för Dynamics 365 for Operations-företag med landskontext som stöder valutanedgång.</td>
<td>NUMERALSTOTEXT (skriver 1234,56, &quot;EN&quot;, &quot;&quot;, FALSKT, 2) returnerar "Ett tusen två hundra trettio fyra och 56" NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, FALSKT, 0) returnerar "Sluta dwadzieścia" NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, SANT, 2) returnerar "евроцент Сто двадцать евро 21"</td>
</tr>
<tr class="odd">
<td>PADLEFT (sträng, längd, teckenutfyllnad)</td>
<td>Returnerar en sträng med angiven längd i vilken den aktuella strängens början är utfylld med angivna tecken.</td>
<td>PADLEFT (“1234”, 10, “ “) returnerar textsträngen “      1234”</td>
</tr>
</tbody>
</table>

### <a name="data-collection-functions"></a>Datainsamlingsfunktioner

Funktion

beskrivning

Exempel

FORMATELEMENTNAME ()

Returnerar namnet på det aktuella formatets element. Returnerar tom sträng när flaggan **Collect output details** är avstängd för aktuella filer.

Se uppgiftsguiden **ER Use data of format output for counting and summing** (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner.

SUMIFS (Ange strängen för summering, Räckvidd1 villkorssträngen, värde1 villkorssträngen \[, Område2 villkorssträngen, värde2 villkorssträngen,... \])

Returnerar en summa av XML-nodvärden (med namnet definierat som en nyckel) som samlats in i samband med denna formatkörning, och som uppfyller angivna villkor (par med intervall och värde). Returnerar nollvärde när flaggan **Collect output details **är avstängd för aktuella filer.

SUMIF (nyckelsträng för summering, sträng för kriteriespann, värdesträng för kriterier)

Returnerar en summa av XML-nodvärden (med namnet definierat som en nyckel) som samlats in i samband med denna formatkörning, och som uppfyller angivet villkor (intervall och värde). Returnerar nollvärde när flaggan **Collect output details** är avstängd för aktuella filer.

COUNTIFS (Räckvidd1 villkorssträngen, värde1 villkorssträngen \[, Område2 villkorssträngen, värde2 villkorssträngen,... \])

Returnerar antalet XML-noder som samlats in i samband med denna formatkörning, och som uppfyller angivna villkor (par med intervall och värde). Returnerar nollvärde när flaggan **Collect output details** är avstängd för aktuella filer.

COUNTIF (intervallsträng för kriterier, värdesträng för kriterier)

Returnerar antalet XML-noder som samlats in i samband med denna formatkörning, och som uppfyller angivet villkor (intervall och värde). Returnerar nollvärde när flaggan **Collect output details** är avstängd för aktuella filer.

COLLECTEDLIST (Räckvidd1 villkorssträngen, värde1 villkorssträngen \[, Område2 villkorssträngen, värde2 villkorssträngen,... \])

Returnerar en lista över XML-nodvärden som har samlats in i samband med denna formatkörning, och som uppfyller angivna villkor (intervall och värde). Returnerar en tom lista när flaggan **Collect output details **är avstängd för aktuella filer.

### <a name="other-business-domainspecific-functions"></a>Andra (företagsdomänspecifika) funktioner

| Funktion                                                                         | beskrivning                                                                                                                                                                                                                                                        | Exempel                                                                                                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CONVERTCURRENCY (amount, source currency, target currency, date, company)        | Konvertera det angivna penningbeloppet från källvalutan till målvalutan genom att använda inställningarna för det specificerade Dynamics 365 for Operations-företaget på angivet datum.                                                                            | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** returnerar motsvarigheten för en euro i US-dollar för det aktuella sessionsdatumet baserat på inställningarna för DEMF-företaget.                                                                                                                                  |
| ROUNDAMOUNT (number, decimals, round rule)                                       | Avrundar det angivna beloppet enligt den definierade avrundningsregeln och det angivna antalet decimaler. **Obs!** Avrundningsregeln måste anges som ett värde för **RoundOffType**-uppräkningen för Dynamics 365 for Operations.                          | Om den **modell. RoundOff** parameter är inställd på *** Downward *** **ROUNDAMOUNT (1000.787, 2 modell. RoundOff)** returnerar värdet **1000.78**. Om **model.RoundOff**-parametern är inställd på **Normal** eller **Rounding-up** returnerar **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** värdet **1000.79**. |
| CURCredRef (digits)                                                              | Returnerar en betalningsmottagarreferens baserad på siffrorna i det angivna fakturanumret.                                                                                                                                                                                  | **CURCredRef ("VEND-200002")** returnerar **"2200002"**.                                                                                                                                                                                                                                                         |
| REST\_97 (siffror)                                                                 | Returnerar en betalningsmottagarreferens som ett MOD97-uttryck baserat på siffrorna i det angivna fakturanumret.                                                                                                                                                            | **REST\_97 ("Lev-200002")** returnerar **"20000285"**.                                                                                                                                                                                                                                                           |
| ISOCredRef (digits)                                                              | Returnerar en ISO-betalningsmottagarreferens baserat på siffror och bokstäver i det angivna fakturanumret. **Obs! **Om du vill ta bort symboler som inte överensstämmer med ISO-standarden från alfabetet måste indataparametern översättas innan den skickas till den här funktionen. | **ISOCredRef ("VEND-200002")** returnerar **"RF23VEND-200002"**.                                                                                                                                                                                                                                                 |
| CN\_GBT\_AdditionalDimensionID (sträng, nummer)                                  | Hämta ID för ytterligare ekonomisk dimension Dimensioner representeras i denna sträng som ID åtskilda med kommatecken. Nummer definierar den begärda dimensionens seriekord i denna sträng.                                                                            | CN\_GBT\_AdditionalDimensionID ("AA, BB, CC, DD, EE, FF, GG, HH", 3) returnerar "Kopia"                                                                                                                                                                                                                                      |
| GetCurrentCompany ()                                                             | Returnerar koden för aktuellt protokollfört företag.                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                               |
| CH\_BANK\_MOD\_10 (siffror)                                                       | Returnerar en betalningsmottagarreferens som ett MOD10-uttryck baserat på siffrorna i det angivna fakturanumret.                                                                                                                                                                      | CH\_BANK\_MOD\_10 ("Lev-200002") returnerar 3                                                                                                                                                                                                                                                                   |
| Anläggningstillgångar\_SUMMA (fasta tillgångar kod, värdekod modell, startdatum, slutdatum)               | Returnerar den förberedda databehållaren för ett anläggningstillgångsbelopp för en period.                                                                                                                                                                                         | Anläggningstillgångar\_SUMMAN ("Dator 000001", "Aktuell", datum1, datum2) returnerar förberedd databehållare för anläggningstillgången "Dator 000001" med "Aktuell" värdemodellen för en period från datum1 till Date2.                                                                                                                        |
| Anläggningstillgångar\_saldo (fast tillgång-koden, värdemodell, Rapporteringsår, Rapporteringsdatum) | Returnerar den förberedda databehållaren för ett anläggningstillgångssaldo. Rapporteringåret måste anges som ett värde på Dynamics 365 for Operations-uppräkningen **AssetYear**.                                                                                           | Anläggningstillgångar\_SUMMA ("Dator 000001", "Aktuell", AxEnumAssetYear.ThisYear, SESSIONTODAY ()) returnerar förberedd databehållare saldon för anläggningstillgången "Dator-000001" med "Aktuell" värdemodellen för den aktuella 365 för operationer sessionsdatum.                                                                |

### <a name="functions-list-extension"></a>Utöka funktionslista

ER stöder utökning av listfunktioner som används i ER-uttryck. Vissa tekniska insatser krävs. Om du vill ha mer information, se [Utöka listan över elektroniska rapporteringfunktioner](general-electronic-reporting-formulas-list-extension.md).

<a name="see-also"></a>Se även
--------

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Utöka listan över elektronisk rapportering (ER)](general-electronic-reporting-formulas-list-extension.md)


