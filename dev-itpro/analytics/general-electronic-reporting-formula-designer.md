---
title: Formeldesigner i elektronisk rapportering
description: "Detta avsnitt avslutar hur du använder formeldesignern inom Elektronisk rapportering (ER). Om du utformar ett format för ett visst elektroniskt dokument i ER kan du använda Microsoft Excel-liknande formler för datatransformering för att uppfylla kraven för det dokumentets överensstämmelse och formatering. Olika typ av funktioner stöds - text, datum och tid, matematisk logik, information, datatypskonvertering och andra (företagsdomänspecifika funktioner.)."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 655a6fd99c0688b13c31c79f3322a287f902e7f1
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017


---

# <a name="formula-designer-in-electronic-reporting"></a>Formeldesigner i elektronisk rapportering

[!include[banner](../includes/banner.md)]


Detta avsnitt avslutar hur du använder formeldesignern inom Elektronisk rapportering (ER). Om du utformar ett format för ett visst elektroniskt dokument i ER kan du använda Microsoft Excel-liknande formler för datatransformering för att uppfylla kraven för det dokumentets överensstämmelse och formatering. Olika typ av funktioner stöds - text, datum och tid, matematisk, logisk, information, datatypskonvertering och andra (företagsdomänspecifika funktioner.).

<a name="formula-designer-overview"></a>Formel designer översikt
-------------------------

Elektronisk rapportering (ER) stöder formeldesignern. Därför kan du vid designtillfället konfigurera uttryck som kan användas för följande uppgifter under körning:

-   Omvandla data från en Microsoft Dynamics 365 for Finance and Operations-databas som ska användas i en ER-datamodell utformad som en datakälla för ER- format (filtrering, gruppering, datatypskonvertering osv.)
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

-   Från Finance and Operations-datakällor och körtidsparametrar till en ER-datamodell.
-   Från en ER-datamodell till ett ER-format.
-   Från Finance and Operations-datakällor och körtidsparametrar till en ER-formatmodell.

Bilden visar hur ett uttryck av den här typen skapas. I det här exemplet returnerar uttrycket värdet i fältet **Intrastat.AmountMST** i tabellen **Intrastat** för Finance and Operations, efter det att värdet har avrundats till två decimaler. [![bild-uttryck-bindning](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg) I följande bild visas hur du kan använda ett uttryck av den här typen. I det här exemplet fylls resultatet av det utformade uttrycket in i komponenten **Transaction.InvoicedAmount** i datamodellen **Momsrapporteringsmodell**. [![bild-uttryck-bindning2](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg) Vid körningstidpunkten kommer den utformade formeln **ROUND (Intrastat.AmountMST, 2)** att avrunda värdet i fältet **AmountMST** för respektive post i registret **Intrastat** till två decimaler, samt fylla i det avrundade värdet i komponenten **Transaction.InvoicedAmount** i datamodellen **Momsrapportering**.

### <a name="data-formatting"></a>Data formatering

ER-formeldesignern kan användas för att definiera uttryck som formaterar data som tagits emot från datakällor, så att dessa data kan skickas som en del av det genererade elektroniska dokumentet. Om du har en formatering som ska tillämpas som en typisk regel och återanvändas för ett format kan du kan införa den formateringen en gång i en formatkonfigurering som en namngiven transformering som har ett formateringsuttryck. Den namngivna transformeringen kan sedan länkas till flera formatkomponenter, vars utdata måste vara formaterade enligt det skapade uttrycket. Bilden nedan visar hur du skapar en transformering av den här typen. I det här exemplet tar **TrimmedString**-transformeringen inkommande data för datatypen **String** och trunkerar inledande och avslutande blanksteg när den returnerar strängvärdet. [![bild-transformering-design](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg) Bilden nedan visar hur en transformering av den här typen kan användas. I det här exemplet finns flera formatkomponenter som skickar text som utdata till det genererande elektroniska dokumentet i körtid och som refererar till **TrimmedString**-transformeringen efter namn. [![bild-transformering-användning](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg) Om formatkomponenter refererar till transformeringen **TrimmedString** (till exempel komponenten **partyName** på föregående bild) innebär detta att text skickas som utmatning till genererande dokument. Texten inkluderar inte inledande eller avslutande blanksteg. Om du har en formatering som måste tillämpas separat kan du införa den formateringen som ett individuellt uttryck för en bindning av en särskild formatkomponent. Bilden visar ett uttryck av den här typen. I det här exemplet är **partyType**-formatkomponenten bunden till datakällan via ett uttryck som omvandlar inkommande data från fältet **Model.Company.RegistrationType** i datakällan till versal text och skickar texten som utdata till det elektroniska dokumentet. [![bild-bindning-med-formel](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Processen flödeskontroll

ER-formeldesignern kan användas för att definiera uttryck som styr processflödet för genererande dokument. Du kan:

-   Definiera villkor som fastställer när processen för att skapa ett dokument måste stoppas.
-   Definiera uttryck som antingen skapar meddelanden till slutanvändaren om stoppade processer eller kastar körningsloggmeddelanden om den pågående processen med att skapa en rapport.
-   Definiera filnamnen på de genererande dokumenten och styr villkoren för hur de skapas.

Varje regel i processen flödeskontroll är utformad som en individuell validering. Bilden nedan visar en validering av den här typen. Här följer en förklaring av konfigureringen i det här exemplet:

-   Valideringen utvärderas när **INSTAT**-noden skapades i den genererande XML-filen.
-   Valideringen stoppar körningsprocessen och returnerar **FALSKT** om listan över transaktioner är tom.
-   Valideringen returnerar ett felmeddelande som innehåller texten i etiketten SYS70894 på användarens valda språk.

[![bild-validering](./media/picture-validation.jpg)](./media/picture-validation.jpg) ER-formeldesignern kan även användas för att definiera ett filnamn för ett genererande elektroniskt dokument och för att styra processen för hur en fil skapas. Bilden nedan visar utformningen av en styrning av ett processflöde av den här typen. Här följer en förklaring av konfigureringen i det här exemplet:

-   Listan över poster från **model.Intrastat**-datakällan delas upp i batchar som var och en innehåller upp till 1 000 poster.
-   Utdata skapar en zip-fil som innehåller en fil i XML-format för varje skapad batch.
-   Ett uttryck returnerar ett filnamn för genererande elektroniska dokument genom att konkatenera filnamnet och filsuffixet. För den andra batchen och alla efterföljande batchar innehåller filnamnet batchens ID som ett suffix.
-   Ett uttryck möjliggör (genom att returnera **SANT**) processen för att skapa en fil för batchar som innehåller minst en post.

[![bild-fil-kontroll](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Grundläggande syntax

ER-uttryck kan innehålla några eller flera av följande element:

-   Konstanter
-   Operatorer
-   Referenser
-   Sökvägar
-   Funktioner

#### <a name="constants"></a>Konstanter

Du kan använda text och numeriska konstanter (värden som inte är beräknade) för att utforma uttryck. I uttrycket **VÄRDE ("100") + 20** används exempelvis den numeriska konstanten 20 och strängkonstanten "100". Uttrycket returnerar det numeriska värdet **120**. ER-formeldesignern stöder escape-sekvenser, vilket innebär att du kan definiera den del av strängen i uttrycket som ska hanteras på ett annat sätt. Till exempel returnerar uttrycket **"Leo Tolstoy" "Krig och fred" "Volym 1"** textsträngen **Leo Tolstoy "Krig och fred" Volym 1**.

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

Ordningen i vilken delarna i ett sammansatt uttryck utvärderas är viktig. Till exempel varierar resultatet av uttrycket **1 + 4/2** beroende på om additions- eller divisionsåtgärden utförs först. Du kan använda parenteser för att explicit definiera hur ett uttryck utvärderas. Om du till exempel vill ange att additionsoperationen ska utföras först kan du ändra det föregående uttrycket till **(1 + 4)/2**. Om ordningen för operationer som ska utföras i ett uttryck inte anges explicit baseras ordningen på standardprioriteten som tilldelats de operatorer som stöds. Följande tabell visar operatorerna och den prioritet som tilldelats respektive operator. Operatorer som har högre prioritet (till exempel 7) utvärderas före operatorer med lägre prioritet (exempelvis 1).

| Prioritet | Operatorer      | Syntax                                                   |
|------------|----------------|----------------------------------------------------------|
| 7          | Gruppering       | ( … )                                                    |
| 6          | Medlemsåtkomst  | … . …                                                    |
| 5          | Funktionsanrop  | … ( … )                                                  |
| 4          | Multiplikation | … \* … … / …                                             |
| 3          | Additiv       | … + … … - …                                              |
| 2          | Jämförelse     | … &lt; … … &lt;= … … =&gt; … … &gt; … … = … … &lt;&gt; … |
| 1          | Separation     | … , …                                                    |

Operatorer på samma rad har samma prioritet. Om ett uttryck omfattar fler än en av dessa operatorer utvärderas uttrycket från vänster till höger. Uttrycket **1 + 6 / 2 \* 3 &gt; 5** returnerar exempelvis **sant**. Vi rekommenderar att du använder parenteser om du explicit vill ange önskad ordning för utvärdering av uttryck för att göra uttrycken enklare att läsa och underhålla.

#### <a name="references"></a>Referenser

Alla datakällor för den aktuella ER-komponenten (en modell eller ett format) som är tillgängliga under utformningen av ett uttryck kan användas som namngivna referenser. Till exempel innehåller den aktuella ER-datamodellen datakällan **ReportingDate** som returnerar ett värde av datatypen **DATETIME**. I syfte att formatera värdet i det genererade dokumentet kan du referera datakällan i följande uttryck: **DATETIMEFORMAT (ReportingDate, "åååå-mm-dd")** Alla tecken i namnet på en refererande datakälla som inte representerar en bokstav i alfabetet, måste föregås av ett inledande enkelt citationstecken. ('). Om namnet på en refererad datakälla innehåller minst en symbol som inte representerar inte en bokstav i alfabetet (exempelvis skiljetecken eller någon annan skriftlig symbol), måste namnet visas inom enkla citattecken. Nedan följer några exempel:

-   Det måste finnas en referens till datakällan **Dagens datum och tid** i ett ER-uttryck enligt följande **'Dagens datum och tid'**.
-   Det måste finnas en referens till metoden **name()** för datakällan **Customers** i ett ER-uttryck enligt följande: **Customers.'name()'**

Observera att följande syntax används för att anropa metoder för Dynamics 365 for Operation-datakällor med parametrar:

- Metoden isLanguageRTL för systemdatakällan med en parameter EN-US för strängdatatypen måste anges i ER-uttryck enligt följande: System.'isLanguageRTL'("EN-US").
- Citationstecken är inte obligatoriska när ett metodnamn innehåller endast alfanumeriska symboler. De är obligatoriska för en metod i en tabell när namnet innehåller parenteser.

När systemets datakälla läggs till en ER-mappning som refererar till programklassen Global för Dynamics 365 for Operation, returnerar uttrycket resultatet FALSKT. Det ändrade uttrycket, System. isLanguageRTL'("AR") returnerar ett booleskt värde som SANT.

Observera att överföring till sådana metodsparametrar kan definieras med följande begränsningar:

- Endast konstanter kan överföras till sådana metoder, vars värde definieras i designläge.
- Endast primitiva (grundläggande) datatyper stöds för sådana parametrar (heltal, realtal, boolesk, sträng, osv.).

#### <a name="path"></a>Sökväg

När ett uttryck refererar till en strukturerad datakälla kan du använda sökvägsdefinitionen för att välja ett specifikt primitivt element i den datakällan. En punkt (.) används för separera enskilda element i en strukturerad datakälla. Till exempel innehåller den aktuella ER-datamodellen datakällan **InvoiceTransactions** som returnerar en lista över poster. Poststrukturen **InvoiceTransactions** innehåller fälten **AmountDebit** och **AmountCredit**, som returnerar numeriska värden. Ett uttryck för att beräkna det fakturerade beloppet kan därför utformas på följande sätt: **InvoiceTransactions.AmountDebit – InvoiceTransactions.AmountCredit**.

#### <a name="functions"></a>Funktioner

Nästa avsnitt innehåller beskrivningar av de funktioner som kan användas i ER-uttryck. Alla datakällor i uttryckets sammanhang (aktuell ER-datamodell eller aktuellt ER-format) och även andra konstanter kan användas som parametrar för anropsfunktioner i enlighet med listan över argument för anropsfunktionen. Till exempel innehåller den aktuella ER-datamodellen datakällan **InvoiceTransactions** som returnerar en lista över poster. Poststrukturen **InvoiceTransactions** innehåller fälten **AmountDebit** och **AmountCredit**, som returnerar numeriska värden. Ett uttryck för att beräkna det fakturerade beloppet kan utformas på följande sätt med hjälp av den inbyggda ER-avrundningsfunktionen: **ROUND (InvoiceTransactions.AmountDebit – InvoiceTransactions.AmountCredit, 2)**.

## <a name="supported-functions"></a>Funktioner som stöds
I följande tabeller finns beskrivningar av datamanipuleringsfunktioner kan användas för att designa ER-datamodeller och ER-rapporter. Listan med funktioner är inte fast och kan utökas av utvecklare. Om du vill se listan över vilka funktioner du kan använda ska du gå till funktionsfönstret i ER-formeldesignern.

### <a name="date-and-time-functions"></a>Datum- och tidsfunktioner

| Funktion                                   | Beskrivning                                                                                                                                                                                                                                                                                                                                                      | Exempel                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ADDDAYS (datetime, days)                   | Lägger till det angivna antalet dagar till det definierade datetime-värdet.                                                                                                                                                                                                                                                                                                | **ADDDAYS (NOW(), 7)** returnerar datum och tid sju dagar framöver.                                                                                                                                                                                                                            |
| DATETODATETIME (date)                      | Konverterar det definierade datumvärdet till ett datetime-värde.                                                                                                                                                                                                                                                                                                            | **DATETODATETIME (CompInfo. ”getCurrentDate()')** returnerar aktuellt sessionsdatum för Dynamics 365 for Operation, 2015-12-24 som **2015-12-24 12:00:00: 00**. I det här exemplet är **CompInfo** en ER-datakälla av typen **Finance and Operations/Table** som refererar till CompanyInfo-tabellen. |
| NOW ()                                     | Returnerar aktuellt datum och aktuell tid för Finance and Operations-servern som ett datetime-värde.                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                       |
| TODAY ()                                   | Returnerar aktuellt datum och aktuell tid för Finance and Operations-servern som ett datumvärde.                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                       |
| NULLDATE ()                                | Returnerar date-värdet **null**.                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                       |
| NULLDATETIME ()                            | Returnerar datetime-värdet **null**.                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                       |
| DATETIMEFORMAT (datetime, format)          | Konverterar det definierade datetime-värdet till en sträng i det definierade formatet. (Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).)                                                                        | **DATETIMEFORMAT (NOW(), "åååå-MM-dd")** returnerar det aktuella datumet för Finance and Operations-serverprogrammet, 2015-12-24, som **"2015-12-24"** enligt det definierade anpassade formatet.                                                                                                          |
| DATETIMEFORMAT (datetime, format, culture) | Konverterar det definierade datetime-värdet till en sträng i det definierade formatet och [kulturen](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), "s", "sv")** returnerar det aktuella datumet för Finance and Operations-programservern, 2015-12-24, som **"2015-12-24"** enligt den valda svenska kulturen.                                                                                                             |
| SESSIONTODAY ()                            | Returnerar aktuellt datum och aktuell tid för Dynamics 365 for Finance and Operations-sessionen som ett datumvärde.                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                       |
| SESSIONNOW ()                              | Returnerar aktuellt datum och tid för Dynamics 365 for Finance and Operations-session som ett datetime-värde.                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                       |
| DATEFORMAT (datum, format)                  | Returnerar en strängrepresentation av datumet med ett angivet format.                                                                                                                                                                                                                                                                                                    | **DATEFORMAT (SESSIONTODAY (), "åååå-mm-dd")** returnerar det aktuella Dynamics 365 for Finance and Operations-sessionsdatumet, 2015-12-24, som "**2015-12-24"**" enligt det definierade anpassade formatet.                                                                                                                      |
| DATEFORMAT (datum, format, kultur)         | Konverterar det angivna datumvärdet till en sträng i det definierade formatet och den definierade [kulturen](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).)     | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** returnerar det aktuella sessionsdatumet för Finance and Operations, 2015-12-24, som **"2015-12-24"** enligt den valda svenska kulturen.                                                                                                                       |
| DAYOFYEAR (datum)              | Returnerar en heltalsrepresentation av antalet dagar mellan 1 januari och det angivna datumet.       | **DAYOFYEAR (DATEVALUE (”01-03-2016”, ”dd-MM-åååå”))** returnerar **61**.
**DAYOFYEAR (DATEVALUE (”01-01-2016”, ”dd-MM-åååå”))** returnerar **1**.                                                                                                                       |

**Funktioner för datakonvertering**

| Funktion                                   | beskrivning                                                                                                                                                                                                                                                                                                                                                      | Exempel                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DATETODATETIME (date)                 | Konverterar det definierade datumvärdet till ett datetime-värde.           | **DATETODATETIME (CompInfo. ”getCurrentDate()')** returnerar aktuellt sessionsdatum för Dynamics 365 for Operation, 2015-12-24 som **2015-12-24 12:00:00: 00**. I detta exempel är **CompInfo** en ER-datakälla av typen **Finance and Operations/register** som refererar till registret **CompanyInfo**.                                                                                                                       |
| DATEVALUE (sträng, format)              | Returnerar en datumpresentation av en sträng i ett angivet format.       | **DATEVALUE ("21-Dec-2016", "dd-MMM-åååå")** returnerar datumet 12/21/2016 enligt angivet anpassat format och standardprogrammets kultur **EN-US**.                                                                                                                       |
| DATEVALUE (sträng, format, kultur)              | Returnerar en datumrepresentation av en sträng med ett angivet format och en angiven kultur.       | **DATEVALUE (”21-Gen-2016”, ”dd-MMM-åååå”, ”IT”)** returnerar datumet 01/21/2016 enligt det anpassade format och den anpassade kultur som angetts. Ett undantag kan uppkomma för denna funktions anrop, **DATEVALUE (”21-Gen-2016”, ”dd-MM-åååå”, ”EN-US”)** informerar dig om att en viss sträng inte identifieras som ett giltigt datum.                                                                                                                       |
| DATETIMEVALUE (sträng, format)              | Returnerar en datetime-presentation av en sträng med ett angivet format.       | **DATETIMEVALUE (”2016-Dec-21 02:55:00”, dd-MMM-åååå tt:mm:ss")** returnerar 2:55:00 AM för den 21 dec 2016 enligt angivet anpassade format och standardprogrammets kultur **EN-US**.                                                                                                                       |
| DATETIMEVALUE (sträng, format, kultur)              | Returnerar en datetime-representation av en strängen med ett angivet format och en angiven kultur.       | **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-åååå tt:mm:ss", “IT”)** returnerar 2:55:00 AM för den 21 dec 2016 enligt ett angivet anpassat format och en anpassad kultur. Ett undantag uppstår för denna funktions anrop, **DATETIMEVALUE (”21-Gen-2016”, 02:55:00", ”dd-MM-åååå” tt:mm:ss”, "EN-US”)** informerar dig om att en viss sträng inte identifieras som giltigt datetime.                                                                                                                       |
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
<td><strong>SPLIT (&quot;abcd&quot;, 3)</strong> returnerar en ny lista som består av två poster som har ett <strong>STRING</strong>-fält. Fältet i den första posten innehåller texten <strong>&quot;abc&quot;</strong>, och fältet i den andra posten innehåller texten <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr class="even">
<td>SPLITLIST (list, number)</td>
<td>Delar upp den angivna listan i batchar som var och en innehåller det definierade antalet poster. Returnerar resultatet som en ny lista med batchar som innehåller följande element:
<ul>
<li>Batchar som vanliga listor (<strong>Värde</strong> komponent)</li>
<li>Det aktuella batchnumret (<strong>Batchnummer</strong> component)</li>
</ul></td>
<td>I följande exempel skapas datakällan <strong>Lines</strong> som en postlista med tre poster som delas upp i batchar som var och en innehåller högst två poster. <a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a> Detta anger den utformade formatlayouten, där bindningar till datakällan <strong>Rader</strong> skapas i syfte att generera utdata i XML-format som innehåller enskilda noder för varje batch och posterna i den. <a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a> Följande utgör resultatet av att köra designformatet. <a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LIST (record 1 [, record 2, ...])</td>
<td>Returnerar en ny lista som skapas från de definierade argumenten.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> returnerar en tom post där fältlistan innehåller alla fält i postlistorna <strong>MainData</strong> och <strong>OtherData</strong>.</td>
</tr>
<tr class="even">
<td>LISTJOIN (list 1, list 2, ...)</td>
<td>Returnerar en konkatenerad lista som skapas från listor med definierade argument.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> returnerar listan över sex poster där ett fält i datatypen <strong>STRING</strong> innehåller enskilda bokstäver.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (list)</td>
<td>Returnerar <strong>SANT</strong> om den definierade listan inte innehåller några element. Annars returneras <strong>FALSKT</strong>.</td>
<td></td>
</tr>
<tr class="even">
<td>EMPTYLIST (list)</td>
<td>Returnerar en tom lista genom att använda den definierade en lista som källa för liststrukturen.</td>
<td><strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> returnerar en ny tom lista som har samma struktur som listan som returneras av funktionen <strong>SPLIT</strong>.</td>
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
<td>Om du anger <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> som en datakälla (DS), returnerar <strong>COUNT( ALLITEMS (DS.Value))</strong> <strong>3</strong>.</td>
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
<td>När <strong>Leverantör</strong> konfigureras som en ER-datakälla som refererar till registret VendTable, returnerar <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> en lista över leverantörer som ingår i leverantörsgrupp 40.</td>
</tr>
<tr class="even">
<td>ENUMERATE (list)</td>
<td>Returnerar en ny lista som består av fasta poster i den definierade listan och som visar följande element:
<ul>
<li>Definierade listposter som vanliga listor (<strong>Värde</strong> komponent)</li>
<li>Den aktuella postens index (<strong>Nummer</strong> komponent)</li>
</ul></td>
<td>I följande exempel är datakällan <strong>Enumerated</strong> skapad som en fast lista över leverantörsposter från datakällan <strong>Vendors</strong>, som refererar till tabellen <strong>VendTable</strong>. <a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a> Detta är formatet där databindningar skapas för att generera utdata i XML-format som innehåller enskilda leverantörer som uppräknade noder. <a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a> Detta är resultatet av att köra det designade formatet. <a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>COUNT (list)</td>
<td>Returnerar det antalet poster i den definierade i listan, om listan inte är tom. Annars returneras <strong>0</strong> (noll).</td>
<td><strong>COUNT (SPLIT(&quot;abcd&quot; , 3))</strong> returnerar <strong>2</strong> eftersom funktionen <strong>SPLIT</strong> skapar en lista som består av två poster.</td>
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
</ul>
<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="GER LISTOFFIELDS function - in format expression" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a> Följande exempel visar de ER-format som är bundna till datakällan tillhörande en postlisttyp som skapades med funktionen LISTOFFIELDS.<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="GER LISTOFFIELDS function - format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>Detta är resultatet av körningen av det utformade formatet.<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="GER LISTOFFIELDS function - format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a><strong>Obs!</strong> Översatt text för etiketter och beskrivningar anges automatiskt i ER-formatutmatningen i enlighet med de språkinställningar som har gjorts för överordnade FILE- och FOLDER-element.</td>
</tr>
<tr class="odd">
<td>STRINGJOIN (lista, fältnamn, avgränsare)</td>
<td>Returnerar en sträng bestående av sammanfogade värden från ett fält i en lista som separerats med en vald avgränsare.</td>
<td>Om du anger SPLIT(“abc” , 1) som en datakälla DS, kommer uttrycket STRINGJOIN (DS, DS.Value, “:”) att returnera “a:b:c”</td>
</tr>
<tr class="even">
<td>SPLITLISTBYLIMIT (lista, gränsvärde, gränskälla)</td>
<td>Delar angiven lista i en ny lista bestående av underlistor och returnerar resultatet i form av innehåll i en postlista. Parametern för gränsvärde anger värdet på den gräns som delar ursprungslistan. Gränskälleparametern anger det steg med vilket totalsumman höjs. Gränsen tillämpas inte på en enskild artikel i angiven lista när gränskällan överskrider angiven gräns.</td>
<td>I följande exempel visas exempelformatet med datakällor. <a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="GER SPLITLISTBYLIMIT - format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="GER SPLITLISTBYLIMIT - datasources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>Detta är resultatformatkörningen som en förenklad lista över varuartiklar.<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="GER SPLITLISTBYLIMIT - output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>I följande exempel visas samma format som justerades för att visa listan över varuartiklar i batchar när ett enskilt parti ska omfatta varor med en totalvikt som inte får överstiga gränsen på 9.<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="GER SPLITLISTBYLIMIT - format 1" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="GER SPLITLISTBYLIMIT - datasources 1" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>Detta är resultatet av den justerade formatkörningen. <a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="GER SPLITLISTBYLIMIT - output 1" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a><strong>Obs!</strong> Gränsen tillämpas inte på den sista artikeln i den ursprungliga listan eftersom värdet (11) i gränskällan (vikt) överskrider angiven gräns (9). Använd antingen funktionen <strong>WHERE</strong> eller uttrycket <strong>Enabled</strong> för respektive formatelement för att ignorera (hoppa över) underlistor i samband med rapportgenerering (vid behov).</td>
</tr>
<tr class="odd">
<td>FILTER (list, villkor)</td>
<td>Returnerar den angivna listan filtrerad för det angivna skicket genom att ändra frågan. Till skillnad från funktionen <strong>WHERE</strong> tillämpas det angivna villkoret i databasnivån till alla ER-datakällor av typen registerpost.</td>
<td>FILTER (Leverantörer, Vendors.VendGroup = &quot;40&quot;) returnerar listan som endast omfattar leverantörer som tillhör leverantörsgrupp “40” när <strong>Leverantör</strong> konfigureras som ER-datakälla som refererar till registret <strong>VendTable</strong>.</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Logiska funktioner

| Funktion                                                                                | beskrivning                                                                                                                                                                                                                                                                     | Exempel                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CASE (uttryck, alternativ 1, resultat 1 \[, alternativ 2, resultat 2\] ... \[, standardresultat\]) | Utvärderar det definierade uttryckets värde mot de definierade alternativa alternativen. Returnerar resultatet av alternativet som är lika med värdet av uttrycket. I annat fall returneras det alternativt angivna standardresultatet (den senaste parameter som inte föregås av ett alternativ). | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "VINTER", "11", "VINTER", "12", "VINTER", "")** returnerar strängen **"VINTER"** om det aktuella Finance and Operations-sessionsdatumet är mellan oktober och december. Annars returneras en tom sträng. |
| IF (condition, value 1, value 2)                                                        | Returnerar det definierade värdet 1, när det definierade kriteriet uppfylls. Annars returneras värde 2. Om värde 1 och värde 2 är poster eller postlistor, kommer resultatet enbart att utgöras av de fält som finns med i båda listorna.                                                                     | **IF (1=2, "condition is met", "condition is not met")** returnerar strängen **"villkoret är inte uppfyllt"**.                                                                                                                                                      |
| NOT (condition)                                                                         | Returnerar det omvända logiska värdet för det definierade kriteriet.                                                                                                                                                                                                                   | **NOT (SANT)** returnerar **FALSKT**.                                                                                                                                                                                                                            |
| OCH (villkor 1\[, villkor 2, ...\])                                                 | Returnerar **SANT** om *alla* definierade kriterier är sanna. Annars returneras **FALSKT**.                                                                                                                                                                                            | **AND (1=1, "a"="a")** returnerar **SANT**. **AND (1=2, "a"="a")** returnerar **FALSKT**.                                                                                                                                                                           |
| ELLER (villkor 1\[, villkor 2, ...\])                                                  | Returnerar **FALSKT** om *alla* definierade kriterier är falska. Returnerar **SANT** om *något* av de definierade kriterierna är sant.                                                                                                                                                                 | **OR (1=2, "a"="a")** returnerar **SANT**.                                                                                                                                                                                                                      |

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
<td><strong>NUMMERVÄRDE(&quot;1 234,56&quot;, &quot;,&quot;, &quot; &quot;)</strong> returnerar värdet <strong>1234.56</strong>.</td>
</tr>
<tr class="even">
<td>VALUE (string)</td>
<td>Konverterar den definierade strängen till ett tal. Kommatecken och punkter (.) betraktas som decimalavgränsare och bindestreck (-) används som ett negativt tecken. Kasta ett undantag om andra icke-numeriska tecken upptäcks i den definierade strängen.</td>
<td><strong>VÄRDE (&quot;1 234,56&quot;)</strong> anger ett undantag.</td>
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

**Funktioner för datakonvertering**

| Funktion             | beskrivning                                                                                                                                                                                                                                     | Exempel                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| VALUE (string) | Konverterar den definierade strängen till ett tal. Kommatecken och punkter (.) betraktas som decimalavgränsare och ett inledande bindestreck (-) används som ett negativt tecken. Ett fel uppstår om andra icke-numeriska tecken upptäcks i den definierade strängen.                                                                                  | **VALUE ("1 234,56")** kastar ett undantag.   |
| NUMBERVALUE (string, decimal separator, digit grouping separator) | Konverterar den definierade strängen till ett tal. Den angivna symbolen används för att åtskilja heltal och decimaler i ett decimaltal. Definierad tusentalsavgränsare används också.                                                                                  | **NUMBERVALUE("1 234,56", ",", " ")** returnerar värdet **1234.56**.    |
| INTVALUE (sträng) | Returnerar heltalsrepresentation av en sträng. Tillgängliga decimaldelar trunkeras.                                                                                  | **INTVALUE (”100.77”)** returnerar **100**. |
| INTVALUE (värde) | Returnerar heltalsrepresentation av ett värde. Tillgängliga decimaldelar trunkeras.                                                                                  | **INTVALUE (-100.77)** returnerar **-100**. |
| INT64VALUE (string) | Returnerar int64-representation av en sträng. Tillgängliga decimaldelar trunkeras.                                                                                  | **INT64VALUE (“22565422744”)** returnerar **22565422744**. |
| INT64VALUE (number) | Returnerar int64-representation av ett värde. Tillgängliga decimaldelar trunkeras.                                                                                  | **INT64VALUE (22565422744.00)** returnerar **22565422744**. |



### <a name="record-functions"></a>Inspelningsfunktioner

| Funktion             | beskrivning                                                                                                                                                                                                                                     | Exempel                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| NULLCONTAINER (list) | Returnerar en **null**-post som har samma struktur som den definierade postlistan eller posten. **Obs!** Den här funktionen är föråldrad. Använd **EMPTYRECORD** i stället.                                                                                  | **NULLCONTAINER (SPLIT ("abc", 1))** returnerar en ny tom post som har samma struktur som listan som returneras från **SPLIT**-funktionen. |
| EMPTYRECORD (record) | Returnerar en **null**-post som har samma struktur som den definierade postlistan eller posten. **Obs!** En **noll**-post (null) är en post där alla fält har ett tomt värde (**0** \[noll\] för siffror, en tom sträng för strängar, och så vidare). | **EMPTYRECORD (SPLIT ("abc", 1))** returnerar en ny tom post som har samma struktur som listan som returneras från **SPLIT**-funktionen.   |

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
<td><strong>ÖVRE(&quot;prov&quot;)</strong> returnerar <strong>&quot;PROV&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LOWER (string)</td>
<td>Returnerar den definierade strängen konverterad till gemener.</td>
<td><strong>LÄGRE (&quot;Prov&quot;)</strong> returnerar <strong>&quot;prov&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>LEFT (string, number of characters)</td>
<td>Returnerar det definierade antalet tecken från början av den definierade strängen.</td>
<td><strong>VÄNSTER (&quot;prov&quot;, 3)</strong> returnerar <strong>&quot;Pr&quot;</strong>.</td>
</tr>
<tr class="even">
<td>RIGHT (string, number of characters)</td>
<td>Returnerar det definierade antalet tecken från slutet av den definierade strängen.</td>
<td><strong>HÖGER (&quot;Prov&quot;, 3)</strong> returnerar <strong>&quot;ov&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>MID (string, starting position, number of characters)</td>
<td>Returnerar det definierade antalet tecken från den definierade strängen, med start från den definierade positionen.</td>
<td><strong>MEL (&quot;Prov&quot;, 2, 3)</strong> returnerar <strong>&quot;ro&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LEN (string)</td>
<td>Returnerar antalet tecken i den definierade strängen.</td>
<td><strong>LEN (&quot;Prov&quot;)</strong> returnerar <strong>6</strong>.</td>
</tr>
<tr class="odd">
<td>CHAR (number)</td>
<td>Returnerar teckensträngen som har en referens till det definierade Unicode-numret.</td>
<td><strong>CHAR (255)</strong> returnerar <strong>&quot;ÿ&quot;</strong>. <strong>Obs!</strong> Den returnerade vilar på den kodning som har valts i det överordnade filformatelementet. Listan över de kodningar som stöds finns i ämnet <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Encoding class</a>.</td>
</tr>
<tr class="even">
<td>CONCATENATE (string 1 [, string 2, …])</td>
<td>Returnera alla definierade textsträngar som är konkatenerade till en sträng.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> returnerar <strong>&quot;abcdef&quot;</strong>. <strong>Obs!</strong> Uttrycket <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> returnerar även <strong>&quot;abcdef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>ÖVERSÄTT (string, pattern, replacement)</td>
<td>Returnerar den definierade strängen i vilken alla förekomster av tecknen i den definierade mönstersträngen ersätts av tecknen på motsvarande position i den definierade utbytessträngen.</td>
<td><strong>ÖVERSÄTT (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> ersätter mönstret <strong>&quot;cd&quot;</strong> med strängen <strong>&quot;GH&quot;</strong> och returnerar <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="even">
<td>REPLACE (string, pattern, replacement, regular expression flag)</td>
<td>När ett definierat reguljärt uttrycks flagga har värdet <strong>sant</strong> returneras den definierade strängen som har ändrats genom att ett reguljärt uttryck som definierats som ett mönsterargument för den här funktionen tillämpas. Uttrycket används för att hitta tecken som måste ersättas. Tecknen i det definierade utbytesargumentet används för att ersätta tecken som hittas. Om flaggan för det definierade reguljära uttrycket har värdet <strong>falskt</strong>uppför sig den här funktionen på samma sätt som <strong>ÖVERSÄTT</strong>.</td>
<td>  <strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, sant)</strong> tillämpar ett standarduttryck som avlägsnar alla icke-numeriska symboler och returnerar <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, falskt)</strong> ersätter mönstret <strong>&quot;cd&quot;</strong> med strängen <strong>&quot;GH&quot;</strong> och returnerar <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TEXT (input)</td>
<td>Returnera den specificerade indatan, som konverteras till en textsträng och formateras i enlighet med serverns lokala inställningar för den aktuella instansen av Finance and Operations. För värden av typen <strong>real</strong> är strängkonverteringen begränsad till två decimaler.</td>
<td>Om serverns lokala inställningar för Finance and Operations anges som <strong>EN-US</strong>, returnerar <strong>TEXT (NOW ())</strong> aktuellt Finance and Operations-sessionsdatum, 2015-12-17, som textsträngen <strong>&quot;12/17/2015 07:59:23 AM&quot;</strong>. <strong>TEXT (1/3)</strong> returnerar <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMAT (string 1, string 2[, string 3, ...])</td>
<td>Returnerar den definierade strängen, som har formaterats genom att byta ut alla förekomster av <strong>%N</strong> med argumentet <em>n</em>. Argumenten är strängar. Om ett argument inte har angetts för en parameter, returneras parametern som <strong>&quot;%N&quot;</strong> i strängen. För värden av typen <strong>real</strong> är strängkonverteringen begränsad till två decimaler.</td>
<td>I det här exemplet returnerar datakällan <strong>PaymentModel</strong> listan över kundposter via komponenten <strong>Customer</strong> och bearbetar datumvärdet via fältet <strong>ProcessingDate</strong>. <a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a> I ER-formatet, som har utformats för att generera en elektronisk fil för utvalda kunder, väljs <strong>PaymentModel</strong> som en datakälla och styr processflödet. Ett undantag kastas för slutanvändare när en vald kund stoppas för det datum då rapporten bearbetas. Formeln, som utformats för denna typ av bearbetningsstyrning, kan endast använda följande resurser:
<ul>
<li>Finance and Operations-etikett SYS70894, som har följande text:
<ul>
<li><strong>För språket EN-US:</strong> &quot;Nothing to print&quot;</li>
<li><strong>För språket SV-SE:</strong> &quot;Inget att skriva ut&quot;</li>
</ul></li>
<li>Finance and Operations-etikett SYS18389, som har följande text:
<ul>
<li><strong>För språket EN-US:</strong> &quot;Customer %1 is stopped for %2.&quot;</li>
<li><strong>För språket SV-SE:</strong> &quot;Gäldenären "%1" spärras för %2.&quot;</li>
</ul></li>
</ul>
Här följer formeln som kan utformas: FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;)) Om en rapport bearbetas för <strong>Litware-butikskunden</strong> den 17 december 2015, i kulturen <strong>EN-US</strong> och språket <strong>EN-US</strong>, så returnerar denna formel följande text, som sedan kan presenteras i form av ett undantagsmeddelande för slutanvändaren: &quot;Nothing to print. Kunden Litware Retail har stoppats för 2015-12-17&quot; Om samma rapport bearbetas för<strong> kunden Litware Retail</strong> den 17 december 2015, kommer denna formel i kulturen <strong>SV</strong> och med språket <strong>SV</strong> att returnera följande text, som använder ett annat datumformat: &quot;Det finns inget att skriva ut. Gäldenären "Litware Retail" spärras dunder 2015-12-17.&quot; <strong>Obs!</strong> Följande syntax används i ER-formler för etiketter:
<ul>
<li><strong>För etiketter från Finance and Operations-resurser:</strong> <strong>@&quot;X&quot;</strong>, där X är etikettens ID i programobjektträdet (Application Object Tree, AOT)</li>
<li><strong>För etiketter i ER-konfigurationer:</strong> <strong>@&quot;SV_LABEL:X&quot;</strong>, där X är etikettens ID i ER-konfigurationen</li>
</ul></td>
</tr>
<tr class="odd">
<td>NUMBERFORMAT (number, format)</td>
<td>Returnerar strängen som representerar det definierade talet i det angivna formatet. (Information om format som stöds finns i <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">standard</a> och <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">anpassade</a>.) Den kontext som denna funktion körs i avgör den kultur som används för att formatera tal.</td>
<td>För kulturen EN-US returnerar <strong>NUMBERFORMAT (0.45, &quot;p&quot;)</strong> <strong>&quot;45.00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> returnerar <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (nummer, språk, valuta, skriv ut flagga för valutanamn, decimaler)</td>
<td>Returnerar angivet nummer (konverterat) till textsträngar på angivet språk.. Språkkoden är valfri: när den definieras som en tom sträng kommer språkkoden för den löpande kontexten (som definierats för en genererande mapp eller fil) att användas i stället. Valutakoden är valfri. När den definieras som en tom sträng, används företagsvalutan. Notera att parametern <strong>Skriv ut valutanamn</strong> och parametern <strong>Decimaler</strong> endast analyseras för följande språkkoder: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong>, <strong>RU</strong>. Notera att parametern <strong>Skriv ut valutanamn</strong> endast analyseras för Finance and Operations-företag med landskontext som stöder valutanedgång.</td>
<td>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, falskt, 2) returnerar "ett tusen två hundra trettio fyra komma 56" NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, falskt, 0) returnerar “Sto dwadzieścia” NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, sant, 2) returnerar “Сто двадцать евро 21 евроцент”</td>
</tr>
<tr class="odd">
<td>PADLEFT (sträng, längd, teckenutfyllnad)</td>
<td>Returnerar en sträng med angiven längd i vilken den aktuella strängens början är utfylld med angivna tecken.</td>
<td>PADLEFT (“1234”, 10, “ “) returnerar textsträngen “      1234”</td>
</tr>
<tr class="even">
<td>TRIM (string)</td>
<td>Returnerar angiven text efter trunkering av inledande och avslutande blanksteg, och avlägsnar multipla blanksteg mellan ord. </td>
<td><strong>TRIM ("     Sample     text     ")</strong> returnerar <strong>"Sample text".</strong></td>
=======
<td>GETENUMVALUEBYNAME (uppräkning av sökväg för datakälla, uppräkning av etikettext för värde)</td>
<td>Returnerar ett värde för en angiven datakälla efter angiven text för denna uppräkningsetikett.</td>
<td>I följande exempel visas ReportDirection-uppräkningen introducerad i en datamodell. Observera att etiketter definieras för uppräkningsvärden.
Följande exempel visar:
<ul><li>Modelluppräkningen <strong>ReportDirection</strong> infogad i en rapport som en datakälla <strong>$Direction</strong></li>
<li>ER-uttrycket <strong>$IsArrivals</strong> utformad att använda modelluppräkning som en parameter för denna funktion. Värdet i det här uttrycket är <strong>SANT</strong></li></ul></td>
</tr>
</tbody>
</table>

**Funktioner för datakonvertering**

| Funktion             | beskrivning                                                                                                                                                                                                                                     | Exempel                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| TEXT (input) | Returnera den specificerade indatan, som konverteras till en textsträng och formateras i enlighet med serverns lokala inställningar för den aktuella instansen av Finance and Operations.
För värden av typen real är strängkonverteringen begränsad till två decimaler.| Om serverns lokala inställningar för Finance and Operations anges som **EN-US, TEXT (NOW ())**, returneras aktuellt Finance and Operations-sessionsdatum, 2015-12-17, som textsträngen **"12/17/2015 07:59:23 AM"**.
**TEXT (1/3) returnerar "0.33"**. |
| QRCODE (sträng) | Returnerar QR-kodbild i binärt base64-format för en given sträng. | **QRCODE (”exempeltext”)** returnerar **U2FtcGxlIHRleHQ =**.   |

### <a name="data-collection-functions"></a>Datainsamlingsfunktioner

| Funktion             | beskrivning                                                                                                                                                                                                                                     | Exempel                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| FORMATELEMENTNAME () | Returnerar namnet på det aktuella formatets element. Returnerar tom sträng när flaggan **Samla in utdatadetaljer** är avstängd för aktuella filer.| Se uppgiftsguiden **ER Använd data från formatutmatningen för inventering och summering** (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner. |
| SUMIFS (nyckelsträng för summering, kriterispann1, kriterievärde1-sträng \[, kriteriespann2-sträng, kriterievärde2-sträng, …\]) |Returnerar en summa av XML-nodvärden (med namnet definierat som en nyckel) som samlats in i samband med denna formatkörning, och som uppfyller angivna villkor (par med intervall och värde). Returnerar nollvärde när flaggan **Samla in utdatadetaljer** är avstängd för aktuella filer. |            |
| SUMIF (nyckelsträng för summering, sträng för kriteriespann, värdesträng för kriterier) | Returnerar en summa av XML-nodvärden (med namnet definierat som en nyckel) som samlats in i samband med denna formatkörning, och som uppfyller angivet villkor (intervall och värde). Returnerar nollvärde när flaggan **Samla in utdatadetaljer** är avstängd för aktuella filer.|           |
| COUNTIFS (sträng för kriteriespann1, sträng för kriterievärde1 \[, sträng för kriteriespann2, sträng för kriterievärde2, …\]) | Returnerar antalet XML-noder som samlats in i samband med denna formatkörning, och som uppfyller angivna villkor (par med intervall och värde). Returnerar nollvärde när flaggan **Samla in utdatadetaljer** är avstängd för aktuella filer.|     |
| COUNTIF (intervallsträng för kriterier, värdesträng för kriterier) | Returnerar antalet XML-noder som samlats in i samband med denna formatkörning, och som uppfyller angivet villkor (intervall och värde). Returnerar nollvärde när flaggan **Samla in utdatadetaljer** är avstängd för aktuella filer.|          |
| COLLECTEDLIST (sträng för kriteriespann1, sträng för kriterievärde1 \[, sträng för kriteriespann2, sträng för kriterievärde2, …\]) | Returnerar en lista över XML-nodvärden som har samlats in i samband med denna formatkörning, och som uppfyller angivna villkor (intervall och värde). Returnerar en tom lista när flaggan **Samla in utdatadetaljer** är avstängd för aktuella filer.|               |   




### <a name="other-business-domainspecific-functions"></a>Andra (företagsdomänspecifika) funktioner

| Funktion                                                                         | beskrivning                                                                                                                                                                                                                                                        | Exempel                                                                                                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CONVERTCURRENCY (amount, source currency, target currency, date, company)        | Konvertera det angivna penningbeloppet från källvalutan till målvalutan genom att använda inställningarna för det specificerade-företaget på angivet datum.                                                                            | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** returnerar motsvarigheten för en euro i US-dollar för det aktuella sessionsdatumet baserat på inställningarna för DEMF-företaget.                                                                                                                                  |
| ROUNDAMOUNT (number, decimals, round rule)                                       | Avrundar det angivna beloppet enligt den definierade avrundningsregeln och det angivna antalet decimaler. **Obs!** Avrundningsregeln måste anges som ett värde för **RoundOffType**-uppräkningen för Finance and Operations.                          | Om parametern **model.RoundOff** anges som ****Downward****, returnerar **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** värdet **1000.78**. Om **model.RoundOff**-parametern är inställd på **Normal** eller **Rounding-up** returnerar **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** värdet **1000.79**. |
| CURCredRef (digits)                                                              | Returnerar en betalningsmottagarreferens baserad på siffrorna i det angivna fakturanumret.                                                                                                                                                                                  | **CURCredRef ("VEND-200002")** returnerar **"2200002"**.                                                                                                                                                                                                                                                         |
| MOD\_97 (siffror)                                                                 | Returnerar en betalningsmottagarreferens som ett MOD97-uttryck baserat på siffrorna i det angivna fakturanumret.                                                                                                                                                            | **MOD\_97 ("VEND-200002")** returnerar **"20000285"**.                                                                                                                                                                                                                                                           |
| ISOCredRef (digits)                                                              | Returnerar en ISO-betalningsmottagarreferens baserat på siffror och bokstäver i det angivna fakturanumret. **Obs!** Om du vill ta bort symboler som inte överensstämmer med ISO-standarden från alfabetet måste indataparametern översättas innan den skickas till den här funktionen. | **ISOCredRef ("VEND-200002")** returnerar **"RF23VEND-200002"**.                                                                                                                                                                                                                                                 |
| CN\_GBT\_AdditionalDimensionID (sträng, nummer)                                  | Hämta ID för ytterligare ekonomisk dimension Dimensioner representeras i denna sträng som ID åtskilda med kommatecken. Nummer definierar den begärda dimensionens seriekord i denna sträng.                                                                            | CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3) returnerar “CC”                                                                                                                                                                                                                                      |
| GetCurrentCompany ()                                                             | Returnerar textrepresentation av en kod för en juridisk person (företag) som en användare inloggad till.                                                                                                                                                                                                                    | **GETCURRENTCOMPANY ()** returnerar **USMF** för en användare som är inloggad på Finance and Operations-företaget **Contoso Entertainment System USA**.                                                                                                                                                                                                                                                                                                              |
| CH\_BANK\_MOD\_10 (siffror)                                                       | Returnerar en betalningsmottagarreferens som ett MOD10-uttryck baserat på siffrorna i det angivna fakturanumret.                                                                                                                                                                      | CH\_BANK\_MOD\_10 ("VEND-200002") returnerar 3                                                                                                                                                                                                                                                                   |
| FA\_SUM (Anläggningstillgångskod, värdemodellkod, startdatum, slutdatum)               | Returnerar den förberedda databehållaren för ett Anläggningstillgångsbelopp för en period.                                                                                                                                                                                         | FA\_SUM ("COMP-000001", “Current”, Date1, Date2) returnerar den förberedda databehållaren för anläggningstillgången "COMP-000001" med värdemodellen "Aktuell" för en period mellan Date1 och Date2.                                                                                                                        |
| FA\_BALANCE (Anläggningstillgångskod, värdemodellkod, rapporteringsår, rapporteringsdatum) | Returnerar den förberedda databehållaren för ett Anläggningstillgångsaldo. Rapporteringsåret måste anges som ett värde för Finance and Operations-uppräkningen **AssetYear**.                                                                                           | FA\_SUM ("COMP-000001", “Current”, AxEnumAssetYear.ThisYear, SESSIONTODAY ()) returnerar den förberedda databehållaren för belopp tillhörande anläggningstillgången "COMP-000001" med värdemodellen “Current” på aktuellt Finance and Operations-sessionsdatum.                                                                |
| TABLENAME2ID (string)                                                       | Returnerar heltalsrepresentationen av ett register-ID för ett givet registernamn.                                                                                                                                                                      | **TABLENAME2ID (”Intrastat”)** returnerar **1510**.                                                                                                                                                                                                                                                                   |
| ISVALIDCHARACTERISO7064 (string)                                                       | Returnerar booleskt värde **SANT** när en given sträng representerar ett giltigt internationellt bankkontonummer (IBAN). Returnerar i annat fall det booleska värdet **FALSKT**.                                                                                                                                                                      | **ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")** returnerar **SANT**. **ISVALIDCHARACTERISO7064 ("AT61")** returnerar **FALSKT**.                                                                                                                                                                                                                                                                   |

### <a name="functions-list-extension"></a>Utöka funktionslista

ER stöder utökning av listfunktioner som används i ER-uttryck. Vissa tekniska insatser krävs. Om du vill ha mer information, se [Utöka listan över elektroniska rapporteringfunktioner](general-electronic-reporting-formulas-list-extension.md).

<a name="see-also"></a>Se även
--------

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Utöka listan över elektronisk rapportering (ER)](general-electronic-reporting-formulas-list-extension.md)




