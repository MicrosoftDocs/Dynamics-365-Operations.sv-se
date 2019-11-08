---
title: Formeldesigner i elektronisk rapportering (ER)
description: Detta avsnitt avslutar hur du använder formeldesignern inom Elektronisk rapportering (ER).
author: NickSelin
manager: kfend
ms.date: 07/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43700d68587cebfb4f897c8a5b619dd4771cc439
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181322"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>Formeldesigner i elektronisk rapportering (ER)

[!include [banner](../includes/banner.md)]

Detta avsnitt avslutar hur du använder formeldesignern inom Elektronisk rapportering (ER). Om du utformar ett format för ett visst elektroniskt dokument i ER kan du använda formler för datatransformering för att uppfylla kraven för dokumentets uppfyllelse och formatering. Dessa formler liknar formler i Microsoft Excel. Formulären ger stöd åt olika typer av funktioner: text, datum och tid, matematik, logik, information, datatypskonvertering och andra (företagsdomänspecifika funktioner).

## <a name="formula-designer-overview"></a>Formel designer översikt

ER stöder formeldesignern. Därför kan du vid designtillfället konfigurera uttryck som kan användas för följande uppgifter under körning:

- Omvandla data som tas emot från en appdatabas och som anges i en ER-datamodell som fungerar som datakälla för ER-format. (Till exempel kan dessa omvandlingar omfatta konvertering, filtrering och gruppering av datatyp.)
- Formatera data som ska skickas till ett skapande elektroniskt dokument i enlighet med layout och villkor för ett specifikt ER-format. (Till exempel kan formateringen göras i enlighet med det begärda språket eller kulturen, eller i enlighet med kodning).
- Kontrollera processen för generering av elektroniska dokument. (Till exempel kan uttryck aktivera eller inaktivera utdata från specifika element av formatet, beroende på bearbetade data. De kan också avbryta processen att skapa dokument eller skicka meddelanden till användare.)

Du kan öppna sidan **Formula designer** när du utför någon av följande åtgärder:

- Binda datakällsartiklar till datamodellkomponenter.
- Binda datakällsartiklar till formatkomponenter
- Slutför underhåll av beräknade fält som är en del av datakällor.
- Definiera synlighetvillkoren för användarnas indataparametrar.
- Utforma transformeringar för ett format.
- Definiera aktiveringsvillkoren för formatets komponenter.
- Definiera filnamnen för formatets FIL-komponenter.
- Definiera villkoren för processtyrningsvalideringarna.
- Definiera meddelandetexten för processtyrningsvalideringar.

## <a name="designing-er-formulas"></a>Utforma ER-formler

### <a name="data-binding"></a>Data bindande

ER-formeldesignern kan användas för att definiera ett uttryck som transformerar data som tagits emot från datakällor så att dessa data kan anges i datakonsumenten vid körning:

- Från appdatakällor och körtidsparametrar till en ER-datamodell
- Från en ER-datamodell till ett ER-format
- Från appdatakällor och körtidsparametrar till en ER-format

Bilden visar hur ett uttryck av den här typen skapas. I det här exemplet avrundar uttrycket värdet i fältet **Intrastat.AmountMST** i tabellen Intrastat till två decimaler och returnerar det avrundade värdet.

[![Data bindande](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

Bilden nedan visar hur ett uttryck av den här typen kan användas. I det här exemplet anges resultatet av det utformade uttrycket i komponenten **Transaction.InvoicedAmount** i datamodellen **Tax reporting model**.

[![Databindning används](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

Vid körning avrundar den designade formeln **ROUND (Intrastat.AmountMST 2)** värdet av fältet **AmountMST** för varje post i tabellen Intrastat till två decimaler. Därefter skrivs det avrundade värdet in i komponenten **Transaction.InvoicedAmount** i datamodellen **Tax reporting**.

### <a name="data-formatting"></a>Data formatering

ER-formeldesignern kan användas för att definiera uttryck som formaterar data som tagits emot från datakällor, så att dessa data kan skickas som en del av det skapade elektroniska dokumentet. Du har kanske en formatering som måste användas som en typisk regel och som ska återanvändas för ett format. Då kan du ange den formateringen en gång för alla i formatkonfigurationen, som en namngiven omvandling som innehåller ett uttryck med formatering. Den namngivna transformeringen kan sedan länkas till flera formatkomponenter, där utdata måste vara formaterade enligt det uttryck du skapade.

Bilden nedan visar hur du skapar en transformering av den här typen. I det här exemplet trunkerar **TrimmedString**-transformeringen inkommande data för datatypen **String** genom att ta bort inledande och avslutande blanksteg. Därefter returneras det trunkerade strängvärdet.

[![Transformering](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

Bilden nedan visar hur en transformering av den här typen kan användas. I det här exemplet skickar flera formatkomponenter text som utdata till det skapande elektroniska dokumentet vid körning. Dessa formatkomponenter hänvisar till **TrimmedString**-transformationen med namn.

[![Transformering används](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

När formatkomponenter, såsom komponenten **partyName** i föregående illustration, hänvisar till transformeringen **TrimmedString** sänds text som utdata till det skapande elektroniska dokumentet. Denna text inkluderar inte inledande eller avslutande blanksteg.

Om du har en formatering som måste tillämpas separat kan du införa den formateringen som ett individuellt uttryck för en bindning av en särskild formatkomponent. Bilden visar ett uttryck av den här typen. I det här exemplet är **partyType**-formatkomponenten bunden till datakällan via ett uttryck som omvandlar inkommande data från fältet **Model.Company.RegistrationType** i datakällan till versal text. Uttrycket skickar sedan texten som utdata till det elektroniska dokumentet.

[![Att tillämpa formatering på en enskild komponent](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Processen flödeskontroll

ER-formeldesignern kan användas för att definiera uttryck som styr processflödet för skapande elektroniska dokument. Du kan utföra följande uppgifter:

- Definiera villkor som fastställer när processen för att skapa ett dokument måste stoppas.
- Definiera uttryck som antingen skapar meddelanden till användaren om stoppade processer eller sänder körningsloggmeddelanden om den pågående processen att skapa en rapport.
- Definiera filnamnen på de skapande elektroniska dokumenten och styr villkoren för hur de skapas.

Varje regel i processen flödeskontroll är utformad som en individuell validering. Bilden nedan visar en validering av den här typen. Här följer en förklaring av konfigureringen i det här exemplet:

- Valideringen utvärderas när **INSTAT**-noden skapas under generering av XML-filen.
- Valideringen stoppar körningsprocessen och returnerar **FALSKT** om listan över transaktioner är tom.
- Valideringen returnerar ett felmeddelande som innehåller texten i etiketten SYS70894 på användarens valda språk.

[![Validering](./media/picture-validation.jpg)](./media/picture-validation.jpg)

ER-formeldesignern kan även användas för att skapa ett filnamn för ett skapande elektroniskt dokument och styra processen för hur en fil skapas. Bilden nedan visar utformningen av en styrning av ett processflöde av den här typen. Här följer en förklaring av konfigureringen i det här exemplet:

- Listan med poster från datakällan **modell. Intrastat-** är uppdelat i batchar. Varje batch innehåller upp till 1 000 poster.
- Utdata skapar en zip-fil som innehåller en fil i XML-format för varje skapad batch.
- Ett uttryck returnerar ett filnamn för skapande elektroniska dokument genom att konkatenera filnamnet och filnamnstillägget. För den andra batchen och alla efterföljande batchar innehåller filnamnet batchens ID som ett suffix.
- Ett uttryck möjliggör (genom att returnera **TRUE**) processen för att skapa en fil för batchar som innehåller minst en post.

[![Filkontroll](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="documents-content-control"></a>Kontroll av dokumentinnehåll

Du kan använda ER-formuldesigner för att konfigurera uttryck som styr vilka data som ska placeras i genererade elektroniska dokument vid körning. Till exempel kan uttryck aktivera eller inaktivera utdata från specifika element av formatet, beroende på bearbetade data och konfigurerad logik. Uttrycket kan anges för ett enskilt formatelement i fältet **Aktiverad** på fliken **Mappning** på sidan **Operations designer**, eftersom ett logiskt villkor returnerar det **booleska** värdet:

-   När **Sant** returneras körs aktuellt formatelement.
-   När **Falskt** returneras hoppas aktuellt formatelement över.

Följande bild visar uttryck av den här typen (versionen, **11.12.11** för formatetkonfigurationen **ISO20022 kreditöverföring (NO)** från Microsoft är ett exempel.) **XMLHeader**-formatkomponenten är konfigurerad för att beskriva strukturen för kreditöverföringsmeddelandet, enligt ISO 20022 XML-meddelandestandarder. Formatkomponenten **XMLHeader/dokument/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/ Ustrd** är konfigurerad för att lägga till det genererade meddelandet, XML-elementet **Ustrd** och lägga remitteringsinformationen i en ostrukturerat format som text i följande XML-element:

-   **PaymentNotes**-komponenten används för att skapa texten i betalningsanteckningarna.
-   **DelimitedSequence**-komponenten genererar kommaavgränsade fakturanummer som används för att kvitta den aktuella kreditöverföringen.

[![Operations designer](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> **PaymentNotes**- och **DelimitedSequence**-komponenterna märks med hjälp av ett frågetecken. Detta innebär att användningen av båda komponenterna är villkorlig, baserat på följande kriterier:

-   Definierad för **PaymentNotes**-komponenten, uttrycket **@.PaymentsNotes< >""** aktiverar (genom att returnera **TRUE**) populationen till XML-elementet **Ustrd**, texten för betalningsanteckningar när den här texten för den aktuella kreditöverföringen inte är tom.

[![Operations designer](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)

-   Definierad för **DelimitedSequence**-komponenten, aktiverar **@.PaymentsNotes=""**-uttryck (genom att returnera **TRUE**) populationen till XML-elementet **Ustrd**, avgränsade med komma fakturanummer som används för att kvitta den aktuella kreditöverföringen när texten för betalningsnoteringar om kreditöverföringen är tom.

[![Operations designer](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)

Baserat på den här inställningen innehåller det genererade meddelandet för varje gäldenär, XML-elementet **Ustrd**, antingen texten på betalningsanteckningar eller, om sådan text är tom, text som avgränsas med komma fakturanummer som används för att kvitta betalningen.

### <a name="basic-syntax"></a>Grundläggande syntax

ER-uttryck kan innehålla några eller flera av följande element:

- Konstanter
- Operatorer
- Referenser
- Sökvägar
- Funktioner

#### <a name="constants"></a>Konstanter

Du kan använda text och numeriska konstanter (värden som inte är beräknade) för att utforma uttryck. I uttrycket **VALUE ("100") + 20** används exempelvis den numeriska konstanten **20** och strängkonstanten **"100"**, och uttrycket returnerar det numeriska värdet **120**. Elektronisk rapportering (ER) formeldesignern stöder escape-sekvenser. Därför kan du ange en uttryckssträng som ska hanteras på olika sätt. Till exempel returnerar uttrycket **"Leo Tolstoy" "Krig och fred" "Volym 1"** textsträngen **Leo Tolstoy "Krig och fred" Volym 1**.

#### <a name="operators"></a>Operatorer

Följande register visar de aritmetiska operatorer du kan använda för att göra grundläggande matematiska operationer såsom addition, subtraktion, multiplikation och division.

| Operatör | Betydelse               | Exempel |
|----------|-----------------------|---------|
| +        | Tillägg              | 1 + 2     |
| -        | Subtraktion, negering | 5-2,-1 |
| \*       | Multiplikation        | 7\*8    |
| /        | Indelning              | 9/3     |

Följande tabell visar de jämförelseoperatorer som stöds. Du kan använda dessa operatorer för att jämföra två värden.

| Operatör | Betydelse                  | Exempel    |
|----------|--------------------------|------------|
| =        | Lika                    | X = Y        |
| &gt;     | Större än             | X&gt;Y     |
| &lt;     | Mindre än                | X&lt;Y     |
| &gt;=    | Större än eller lika med | X&gt;=Y    |
| &lt;=    | Mindre än eller lika med    | X&lt;=Y    |
| &lt;&gt; | Inte lika med             | X&lt;&gt;Y |

Dessutom kan du använda ett och-tecken (&) som en operator för textkonkatenering. På så sätt kan du koppla eller konkatenera en eller flera textsträngar till ett enda textstycke.

| Operatör | Betydelse     | Exempel                                             |
|----------|-------------|-----------------------------------------------------|
| &        | Sammanfoga | "Det finns inget att skriva ut" & ":&nbsp;" & "inga poster hittades" |

##### <a name="operator-precedence"></a>Operatorprioritet

Ordningen i vilken delarna i ett sammansatt uttryck utvärderas är viktig. Till exempel är det skillnad på resultatet av uttrycket **1 + 4 / 2** beroende på om additionsoperationen eller divisionsoperationen utförs först. Du kan använda parenteser för att explicit definiera hur ett uttryck utvärderas. Om du till exempel vill ange att additionsoperationen ska göras först kan du ändra det föregående uttrycket till **(1 + 4) / 2**. Om ordningen för operationer som ska utföras i ett uttryck inte uttryckligen rangordnas baseras ordningen på standardprioriteten som tilldelats de operatorer som stöds. Följande register visar den rangordning som tilldelats respektive operator. Operatorer som har en högre prioritet (till exempel 7) utvärderas före operatorer med en lägre prioritet (exempelvis 1).

| Prioritet | Operatorer      | Syntax                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Gruppering       | ( … )                                                                   |
| 6          | Medlemsåtkomst  | … . …                                                                   |
| 5          | Funktionsanrop  | … ( … )                                                                 |
| 4          | Multiplikation | … \* …<br>… / …                                                         |
| 3          | Additiv       | … + …<br>… - …                                                          |
| 2          | Jämförelse     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Separation     | … , …                                                                   |

Om ett uttryck omfattar flera på varandra följande operatorer med samma rangordning, utvärderas dessa åtgärder från vänster till höger. Uttrycket **1 + 6 / 2 \* 3 &gt; 5** returnerar exempelvis **sant**. Vi rekommenderar att du använder parenteser om du explicit vill ange önskad ordning för utvärdering av uttryck så att uttrycken blir enklare att läsa och underhålla.

#### <a name="references"></a>Referenser

Alla datakällor för den aktuella ER-komponenten som är tillgängliga under utformningen av ett uttryck kan användas som namngivna referenser. (Den aktuella komponenten ER kan vara antingen en modell eller ett format.) Aktuell ER-datamodell innehåller exempelvis datakällan **ReportingDate** och denna datakälla returnerar ett värde av datatypen **DATETIME**. I syfte att korrekt formatera värdet i skapande dokument kan du referera datakällan i uttrycket på följande sätt: **DATETIMEFORMAT (ReportingDate, "dd-mm-yyyy")**.

Alla tecken i referenser till en datakälla som inte representerar en bokstav i alfabetet måste föregås av en apostrof ('). Om namnet på en refererad datakälla innehåller minst en symbol som inte representerar inte en bokstav i alfabetet måste namnet visas inom enkla citattecken. (Dessa icke-alfabetiska symboler kan till exempel vara skiljetecken eller andra skrivna symboler.) Här följer några exempel:

- I ett ER-uttryck måste en referens till datakällan **dagens datum och tid** skrivas enligt följande **'Today''s date & time'**.
- I ett ER-uttryck måste kundens namn **name()** för datakällan **Customers** anges enligt följande **Customers.'name()'**.

Om appdatakällor har parametrar måste följande syntax användas för att anropa dessa metoder:

- Om metoden **isLanguageRTL** i datakällan **System** har en **EN-US**-parameter av typen **String** så måste denna anges på följande sätt **System.'isLanguageRTL'("EN-US")** i ett ER-uttryck.
- Det krävs inga citationstecken när ett metodnamn innehåller endast alfanumeriska symboler. Dock är de obligatoriska för en metod i en tabell när namnet innehåller parenteser.

När datakällan **System** läggs till en ER-mappning som refererar till programklassen **Global** returnerar uttrycket ett booleskt värde **FALSE**. Det ändrade uttrycket **Systemet.' isLanguageRTL'("AR")** returnerar det booleska värdet **TRUE**.

Du kan begränsa hur värden skickas till parametrarna för den här typen av metod:

- Endast konstanter kan överföras till metoder av den här typen. Värdena för konstanterna definieras i designläge.
- Endast primitiva (grundläggande) datatyper stöds för parametrar av den här typen. (Primitiva datatyper är integer, real, boolesk, sträng osv).

#### <a name="paths"></a>Sökvägar

När ett uttryck refererar till en strukturerad datakälla kan du använda sökvägsdefinitionen för att välja ett specifikt primitivt element i den datakällan. En punkt (.) används för separera enskilda element i en strukturerad datakälla. Till exempel innehåller den aktuella ER-datamodellen datakällan **InvoiceTransactions**, och denna returnerar en lista över poster. Poststrukturen **InvoiceTransactions** innehåller fälten **AmountDebit** och **AmountCredit**, som båda returnerar numeriska värden. Ett uttryck för att beräkna det fakturerade beloppet kan därför utformas på följande sätt: **InvoiceTransactions.AmountDebit – InvoiceTransactions.AmountCredit**.

#### <a name="functions"></a>Funktioner

Nästa avsnitt innehåller beskrivningar av de funktioner som kan användas i ER-uttryck. Alla datakällor i uttryckets sammanhang (aktuell ER-datamodell eller aktuellt ER-format) kan användas som parametrar för anropsfunktioner i enlighet med listan över argument för anropsfunktionen. Konstanter kan också användas som parametrar av anropsfunktioner. Till exempel innehåller den aktuella ER-datamodellen datakällan **InvoiceTransactions**, och denna returnerar en lista över poster. Poststrukturen **InvoiceTransactions** innehåller fälten **AmountDebit** och **AmountCredit**, som båda returnerar numeriska värden. Ett uttryck för att beräkna det fakturerade beloppet kan utformas på följande sätt med hjälp av den inbyggda ER-avrundningsfunktionen: **ROUND (InvoiceTransactions.AmountDebit – InvoiceTransactions.AmountCredit, 2)**.

## <a name="supported-functions"></a>Funktioner som stöds

I följande tabeller finns beskrivningar av datamanipuleringsfunktioner kan användas för att designa ER-datamodeller och ER-rapporter. Listan över funktioner är inte fast. Utvecklare kan utöka den. Om du vill se listan över vilka funktioner du kan öppna ska du gå till funktionsfönstret i ER-formeldesignern.

### <a name="date-and-time-functions"></a>Datum- och tidsfunktioner

| Funktion | Beskrivning | Exempel |
|----------|-------------|---------|
| ADDDAYS (datetime, days) | Lägg till det angivna antalet dagar till det definierade värdet för datum/tid. | **ADDDAYS (NOW(), 7)** returnerar datum och tid sju dagar framöver. |
| DATETODATETIME (date) | Konvertera det angivna datumvärdet till ett värde för datum/tid. | **DATETODATETIME (CompInfo. ”getCurrentDate()')** returnerar aktuellt sessionsdatum för Finance and Operations, 2015-12-24 som **2015-12-24 12:00:00: 00**. I det här exemplet är **CompInfo** en ER-datakälla av typen **Finance and Operations/Table** och refererar till CompanyInfo-tabellen. |
| NOW () | Returnerar aktuellt programserverdatum och tid som ett datum/tidsvärde. | |
| TODAY () | Returnerar aktuellt programserverdatum och tid som ett datumvärde. | |
| NULLDATE () | Returnerar date-värdet **null**. | |
| NULLDATETIME () | Returnerar värdet för datum/tid som **noll**. | |
| DATETIMEFORMAT (datetime, format) | Konverterar det definierade värdet för datum/tid till en sträng i det angivna formatet. (Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), "dd-MM-yyyy")** returnerar det aktuella datumet för serverprogrammet, 2015-12-24, som **"2015-12-24"** baserat på det definierade och anpassade formatet. |
| DATETIMEFORMAT (datetime, format, culture) | Konverterar det definierade värdet för datum/tid till en sträng i det angivna formatet och [kulturen](https://msdn.microsoft.com/goglobal/bb896001.aspx). (Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), "s", "sv")** returnerar det aktuella datumet för programservern, 2015-12-24, som **"2015-12-24"** baserat på den valda svenska kulturen. |
| SESSIONTODAY () | Returnerar aktuellt programsessionsdatum och tid som ett datumvärde. | |
| SESSIONNOW () | Returnerar aktuellt programsessionsdatum och tid som ett datum/tidsvärde. | |
| DATEFORMAT (datum, format) | Returnera en sträng som representerar det definierade datumet i det angivna formatet. | **DATEFORMAT (SESSIONTODAY () "dd-MM-yyyy")** returnerar det aktuella datumet för programsessionen, 2015-12-24, som **"2015-12-24"** baserat på det definierade och anpassade formatet. |
| DATEFORMAT (datum, format, kultur) | Konverterar det angivna datumvärdet till en sträng i det definierade formatet och den definierade [kulturen](https://msdn.microsoft.com/goglobal/bb896001.aspx). (Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** returnerar det aktuella datumet för programsessionen, 2015-12-24, som **"2015-12-24"** baserat på den valda tyska kulturen. |
| DAYOFYEAR (datum) | Returnera en heltalsrepresentation av antalet dagar mellan 1 januari och det angivna datumet. | **DAYOFYEAR (DATEVALUE (”01-03-2016”, ”dd-MM-åååå”))** returnerar **61**. **DAYOFYEAR (DATEVALUE (”01-01-2016”, ”dd-MM-åååå”))** returnerar **1**. |
| DAGAR (datum 1, datum 2) | Returnera antalet dagar mellan första och andra angivna datum. Returnerar ett positivt värde när det första datumet är senare än det andra, returnerar **0** (noll) när det första datumet är lika med det andra, annars ett negativt värde när det första datumet är tidigare än det andra datumet. | **DAYS (TODAY (), DATUMVÄRDE (DATETIMEFORMAT (ADDDAYS(NOW() 1), ”yyyyMMdd”), ”yyyyMMdd”))** returnerar **-1**. |

### <a name="data-conversion-functions"></a>Funktioner för datakonvertering

| Funktion | beskrivning | Exempel |
|----------|-------------|---------|
| DATETODATETIME (date) | Konvertera det angivna datumvärdet till ett värde för datum/tid. | **DATETODATETIME (CompInfo. ”getCurrentDate()')** returnerar aktuellt sessionsdatum för Finance and Operations, 2015-12-24 som **2015-12-24 12:00:00: 00**. I det här exemplet är **CompInfo** en ER-datakälla av typen **Finance and Operations/Table** och refererar till CompanyInfo-tabellen. |
| DATEVALUE (sträng, format) | Returnera en datumrepresentation för den definierade strängen i angivet format. | **DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")** returnerar datumet 2016-12-24 baserat på angivet anpassat format och standardprogrammets kultur **EN-US**. |
| DATEVALUE (sträng, format, kultur) | Returnera en datumrepresentation för den definierade strängen enligt angivet format och kultur. | **DATEVALUE (”21-Gen-2016”, ”dd-MMM-yyyy”, ”IT”)** returnerar datumet januari 21 2016, enligt format och kultur som angivits och anpassats. Men **DATUMVÄRDE (”21-Gen-2016”, ”dd-MMM-yyyy”, ”EN-US”)** ska utlösa ett undantag som informerar användaren om att den angivna strängen inte identifieras som ett datum. |
| DATETIMEVALUE (sträng, format) | Returner en datum/tidsrepresentation för den definierade strängen i angivet format. | **DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")** returnerar 2:55:00: 00 på 21 December 2016 utifrån angivna och anpassade format och standardprogrammets **engelska** kultur. |
| DATETIMEVALUE (sträng, format, kultur) | Returnera en datum/tidsrepresentation för den definierade strängen enligt angivet format och kultur. | **DATETIMEVALUE (”21-Dec-2016 02:55:00”, "dd-MMM-yyyy hh:mm:ss", "IT")** returnerar 2:55:00:00 21 December 2016 utifrån angivna och anpassade format och standardprogrammets italienska kultur. Men **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")** ska utlösa ett undantag som informerar användaren om att den angivna strängen inte identifieras som ett värde för datum/tid. |

### <a name="list-functions"></a>Lista över funktioner

<table>
<thead>
<tr>
<th>Funktion</th>
<th>beskrivning</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr>
<td>SPLIT (input, length)</td>
<td>Delar upp den definierade indatasträngen i delsträngar som var och en är av den definierade längden. Returnerar resultatet som en ny lista.</td>
<td><strong>SPLIT (&quot;abcd&quot;, 3)</strong> returnerar en ny lista som består av två poster som har ett <strong>STRING</strong>-fält. Fältet i den första posten innehåller texten <strong>&quot;abc&quot;</strong>, och fältet i den andra posten innehåller texten <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr>
<td>SPLIT (indata, avgränsare)</td>
<td>Delar upp den definierade indatasträngen i delsträngar baserat på den definierade avgränsaren.</td>
<td><strong>SPLIT (&quot;XAb aBy&quot;, &quot;aB&quot;)</strong> returnerar en ny lista som består av tre poster som har ett <strong>STRING</strong>-fältet. Fältet i den första posten innehåller texten <strong>&quot;X&quot;</strong>, fältet i den andra posten innehåller texten &quot;&nbsp;&quot;, och fältet i den tredje posten innehåller texten <strong>&quot;y&quot;</strong>. Om avgränsaren är tom returneras en ny lista som består av en post med ett <strong>STRING</strong>-fält som innehåller indatatexten. Om indata är tomt returneras en tom ny lista.
Om antingen indata eller avgränsaren är ospecificerad (null) kastas ett programundantag.</td>
</tr>
<tr>
<td>SPLITLIST (list, number)</td>
<td>Delar upp den angivna listan i batchar som var och en innehåller det definierade antalet poster. Returnerar resultatet som en ny lista med batchar som innehåller följande element:
<ul>
<li>Batchar som vanliga listor (<strong>Värde</strong> komponent)</li>
<li>Det aktuella batchnumret (<strong>Batchnummer</strong> component)</li>
</ul>
</td>
<td>Följande bild visar hur en datakälla på en <strong>rad</strong> skapas av tre poster. Den här listan är indelad i batchar som innehåller högst två poster.
<p><a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>Följande illustration visar layouten på det designade formatet. I den här formatlayouten skapas bindningar till datakällans <strong>rader</strong> för att skapa utdata i XML-format. Dessa utdata visar enskilda noder för varje batch och poster i den.</p>
<p><a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a></p>
<p>Följande illustration visar resultatet när det designade formatet har körts.</p>
<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>
</td>
</tr>
<tr>
<td>LIST (post 1 [, post 2, ...])</td>
<td>Returnerar en ny lista som skapas från de definierade argumenten.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> returnerar en tom post där fältlistan innehåller alla fält i postlistorna <strong>MainData</strong> och <strong>OtherData</strong>.</td>
</tr>
<tr>
<td>LISTJOIN (list 1, list 2, ...)</td>
<td>Returnerar en konkatenerad lista som skapas från listor med definierade argument.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> returnerar en lista över sex poster där ett fält i datatypen <strong>STRING</strong> innehåller enskilda bokstäver.</td>
</tr>
<tr>
<td>ISEMPTY (list)</td>
<td>Returnerar <strong>TRUE</strong> om den definierade listan inte innehåller några element. Annars returneras <strong>FALSKT</strong>.</td>
<td></td>
</tr>
<tr>
<td>EMPTYLIST (list)</td>
<td>Returnerar en tom lista genom att använda den definierade en lista som källa för liststrukturen.</td>
<td><strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> returnerar en ny tom lista som har samma struktur som listan som returneras av funktionen <strong>SPLIT</strong>.</td>
</tr>
<tr>
<td>FIRST (list)</td>
<td>Returnerar den första posten i den definierade listan, om posten inte är tom. I annat fall kastas ett undantag.</td>
<td></td>
</tr>
<tr>
<td>FIRSTORNULL (list)</td>
<td>Returnerar den första posten i den definierade listan, om posten inte är tom. I annat fall returneras en <strong>null</strong>-post.</td>
<td></td>
</tr>
<tr>
<td>LISTOFFIRSTITEM (list)</td>
<td>Returnerar en lista som endast innehåller det första objektet i den definierade listan.</td>
<td></td>
</tr>
<tr>
<td>ALLITEMS (path)</td>
<td>Den här funktionen körs som ett urval i minnet. Returnerar en ny platt lista som representerar alla artiklar som matchar den definierade sökvägen. Sökvägen måste anges som en giltig datakällsökväg för ett datakällselement av datatypen ”postlista”. Dataelement som sökväg och datum bör skapa ett fel i ER-uttrycksgeneratorn vid designtidpunkten.</td>
<td>Om du anger <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> som en datakälla (DS), returnerar <strong>COUNT( ALLITEMS (DS.Value))</strong> <strong>3</strong>.</td>
</tr>
<tr>
<td>ALLITEMSQUERY (sökväg)</td>
<td>Den här funktionen körs som en sammanslagen SQL-fråga. Returnerar en ny platt lista som representerar alla artiklar som matchar den definierade sökvägen. De angivna sökvägen måste anges som en giltig datakällsökväg för ett datakällselement av datatypen ”postlista” och den måste innehålla minst en relation. Dataelement som sökväg och datum bör skapa ett fel i ER-uttrycksgeneratorn vid designtidpunkten.</td>
<td>Definiera följande datakällor i din modellmappning:
<ul>
<li><strong>CustInv</strong> (typen <strong>Registerposter</strong>), som refererar till tabellen CustInvoiceTable</li> 
<li><strong>FilteredInv</strong> (typen <strong>beräknat fält</strong>), som innehåller uttrycket <strong>FILTER (CustInv, CustInv.InvoiceAccount = &quot;US-001&quot;)</strong></li>
<li><strong>JourLines</strong> (typen <strong>beräknat fält</strong> ), som innehåller uttrycket <strong>ALLITEMSQUERY (FilteredInv.'&lt;Relations'.CustInvoiceJour.'&lt;Relations'.CustInvoiceTrans)</strong></li>
</ul>
<p>När du kör en modellmappning att anropa datakällan <strong>JourLines</strong>, kör följande SQL-sats:</p>
VÄLJ ... FRÅN CUSTINVOICETABLE T1 KORSKOPPLA CUSTINVOICEJOUR T2 KORSKOPPLA CUSTINVOICETRANS T3 DÄR...
</td>
</tr>
<tr>
<td>ORDERBY (list [, expression 1, expression 2, …])</td>
<td>Returnera den angivna listan efter att den sorterats enligt de angivna argumenten. Du kan definiera följande argument som uttryck.</td>
<td>Om <strong>Vendor</strong> konfigureras som en ER-datakälla som refererar till tabellen VendTable, <strong>ORDERBY (Vendors, Vendors.'name()')</strong> returneras en lista med leverantörerna sorterade efter namn i stigande ordning.</td>
</tr>
<tr>
<td>REVERSE (list)</td>
<td>Returnerar den definierade listan i omvänd sorteringsordning.</td>
<td>Om <strong>Vendor</strong> konfigureras som en ER-datakälla som refererar till tabellen VendTable, <strong>REVERSE (ORDERBY (Vendors, Vendors.'name()')) )</strong> returneras en lista med leverantörerna sorterade efter namn i fallande ordning.</td>
</tr>
<tr>
<td>WHERE (list, condition)</td>
<td>Returnera den angivna listan efter att den filtrerats enligt de angivna argumenten. Det angivna villkoret används i listan i minnet. På så sätt kan funktionen <strong>WHERE</strong> skilja sig från funktionen <strong>FILTER</strong>.</td>
<td>Om <strong>Vendor</strong> konfigureras som en ER-datakälla som refererar till registret VendTable, returnerar <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> en lista över just de leverantörer som ingår i leverantörsgrupp 40.</td>
</tr>
<tr>
<td>ENUMERATE (list)</td>
<td>Returnerar en ny lista som består av fasta poster i den definierade listan och som visar följande element:
<ul>
<li>Definierade listposter som vanliga listor (<strong>Värde</strong> komponent)</li>
<li>Den aktuella postens index (<strong>Nummer</strong> komponent)</li>
</ul>
</td>
<td>I följande illustration har datakällan <strong>Enumerated</strong> skapat en numrerad lista över leverantörsposter från datakällan <strong>Vendors</strong> som refererar till tabellen VendTable.
<p><a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a></p>
<p>På bilden nedan visas formatet. I den här formatlayouten skapas bindningar för att skapa utdata i XML-format. Dessa utdata visar enskilda leverantörer som fasta noder.</p>
<p><a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a></p>
<p>Följande illustration visar resultatet när det designade formatet har körts.</p>
<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>
</td>
</tr>
<tr>
<td>COUNT (list)</td>
<td>Returnerar det antalet poster i den definierade i listan, om listan inte är tom. Annars returneras <strong>0</strong> (noll).</td>
<td><strong>COUNT (SPLIT(&quot;abcd&quot; , 3))</strong> returnerar <strong>2</strong> eftersom funktionen <strong>SPLIT</strong> skapar en lista som består av två poster.</td>
</tr>
<tr>
<td>LISTOFFIELDS (sökväg)</td>
<td>Returnera en postlista som har skapats av ett argument tillhörande en av följande typer:
<ul>
<li>Uppräkning för modell</li>
<li>Formatuppräkning</li>
<li>Behållare</li>
</ul>
<p>Listan som skapas består av poster som innehåller följande fält:</p>
<ul>
<li>Namn</li>
<li>Etikett</li>
<li>beskrivning</li>
</ul>
I samband med körning returnerar fälten <strong>Label</strong> och <strong>Description</strong> värden baserade på formatets språkinställningar.
</td>
<td>I följande illustration introduceras en uppräkning i datamodellen.
<p><a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a></p>
<p>Illustrationen som följer visar dessa detaljer:</p>
<ul>
<li>Modelluppräkningen har infogats i en rapport som en datakälla.</li>
<li>ER-uttryck använder uppräkningsmodellen som en parameter för funktionen <strong>LISTOFFIELDS</strong>.</li>
<li>En datakälla av typen postlista infogas i en rapport med hjälp av det ER-uttryck som skapats.</li>
</ul>
<p><a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a></p>
<p>Följande exempel visar de ER-formatelement som är kopplade till en datakälla av typen postlista som skapats med funktionen <strong>LISTOFFIELDS</strong>.</p>
<p><a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a></p>
<p>Följande illustration visar resultatet när det designade formatet har körts.</p>
<p><a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a></p>
<blockquote>[!NOTE] Baserat på språkinställningarna i de överordnade FILE- och FOLDER-elementen infogas översatt text för etiketter och beskrivningar i utdata till ER-formatet.</blockquote>
</td>
</tr>
<tr>
<td>LISTOFFIELDS (sökvägen, språk)</td>
<td>Returnera en postlista som skapas från ett argument, t ex en modelluppräkning, en formatuppräkning eller en behållare. Listan som skapas består av poster som innehåller följande fält:
<ul>
<li>Namn</li>
<li>Etikett</li>
<li>beskrivning</li>
<li>Är översatt</li>
</ul>
I samband med körning returnerar fälten <strong>Label</strong> och <strong>Description</strong> värden baserade på formatets språkinställningar och angivet språk. Fältet <strong>Is translated</strong> anger att fältet <strong>Label</strong> har översatts till det angivna språket.
</td>
<td>Till exempel kan du använda datakälltypen <strong>Calculated field</strong> för att konfigurera datakällor för <strong>enumType_de</strong> och <strong>enumType_deCH</strong> till uppräkning av datamodell <strong>enumType</strong>.
<ul>
<li>enumType_de = <strong>LISTOFFIELDS</strong> (enumType, &quot;de&quot;)</li>
<li>enumType_deCH = <strong>LISTOFFIELDS</strong> (enumType, &quot;de-CH&quot;)</li>
</ul>
<p>I det här fallet kan du använda följande uttryck för att få etiketten på uppräkningsvärdet på tyska (Schweiz), om denna översättning är tillgänglig. Om schweizisk tysk översättning inte är tillgänglig är etiketten på tyska.</p>
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
</td>
</tr>
<tr>
<td>STRINGJOIN (lista, fältnamn, avgränsare)</td>
<td>Returnera en sträng som består av de konkatenerade värdena från det definierade fältet från den angivna listan. Värdena avgränsas med angivna avgränsare.</td>
<td>Om du anger <strong>SPLIT(&quot;abc&quot; , 1)</strong> som datakälla (DS), <strong>STRINGJOIN (DS, DS.Value, &quot;-&quot;)</strong> returnerar <strong>&quot;a-b-c&quot;</strong>.</td>
</tr>
<tr>
<td>SPLITLISTBYLIMIT (lista, gränsvärde, gränskälla)</td>
<td>Dela angiven lista i en ny lista bestående av underlistor och returnera resultatet i form av innehåll i en postlista. Parametern <strong>gränsvärde</strong> definierar värdet på den gräns som delar ursprungslistan. Parametern <strong>gränsvärde</strong> definierar värdet på den gräns som delar ursprungslistan. Gränsen tillämpas inte på en enskild artikel i ursprungslistan när gränskällan överskrider angiven gräns.</td>
<td>På bilden nedan visas ett format. 
<p><a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a></p>
<p>I följande illustrationer visar de datakällor som används för det formatet.</p>
<p><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a></p>
<p>Följande illustration visar resultatet när formatet har körts. I det här fallet är resultatet en förenklad lista över varuartiklar.</p>
<p><a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a></p>
<p>I följande exempel visas samma format som har justerats för att visa listan med varuartiklar i batchar, där varje enskild batch måste innehålla varuartiklar och inte överskrida gränsen på 9.</p>
<p><a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a></p>
<p><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a></p>
<p>Följande illustration visar resultatet när det anpassade formatet har körts.</p>
<p><a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a></p>
<blockquote>[!NOTE] Gränsen tillämpas inte på den sista artikeln i den ursprungliga listan eftersom värdet (11) i gränskällan (vikt) överskrider angiven gräns (9). Använd antingen funktionen <strong>WHERE</strong> eller uttrycket <strong>Enabled</strong> för respektive formatelement för att ignorera (hoppa över) underlistor i samband med rapportgenerering, efter behov.</blockquote>
</td>
</tr>
<tr>
<td>FILTER (list, villkor)</td>
<td>Returnera den angivna listan efter att frågan har ändrats för att filtrerats enligt de angivna villkoren. Till skillnad från funktionen <strong>WHERE</strong> tillämpas angivet villkor på alla ER-datakällor av typen <strong>Table records</strong> på databasnivå. Listan och villkoret kan definieras med hjälp av tabeller och relationer.</td>
<td>Om <strong>Vendor</strong> konfigureras som en ER-datakälla som refererar till registret VendTable, returnerar <strong>FILTER(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> en lista över just de leverantörer som ingår i leverantörsgrupp 40. Om <strong>Leverantör</strong> konfigureras som en ER-datakälla som hänvisar till registret och om <strong>parmVendorBankGroup</strong> konfigureras som en ER-datakälla som returnerar ett värde av datatypen <strong>Sträng</strong>, returnerar <strong>FILTER (Vendor.'&lt;Relations'.VendBankAccount, Vendor.'&lt;Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)</strong> en lista över just de leverantörskonton som tillhör en viss bankgrupp.</td>
</tr>
<tr>
<td>INDEX (lista, index)</td>
<td>Den här funktionen returnerar en post som väljs av ett specifikt numeriskt index i listan. Ett undantag erhålls om indexet ligger utanför intervallet för posterna i listan.</td>
<td>Om du anger datakällans <strong>DS</strong> för typen <strong>Beräknat fält</strong> och den innehåller uttrycket <strong>SPLIT ("A|B|C", “|”), 2</strong>, kommer uttrycket <strong>DS.Value</strong> returnera textvärdet “B”. Uttrycket <strong>INDEX (SPLIT ("A|B|C", “|”), 2).Value</strong> returnerar även text värde "B".</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Logiska funktioner

| Funktion | Beskrivning | Exempel |
|----------|-------------|---------|
| CASE (expression, option 1, result 1 \[, option 2, result 2\] … \[, default result\]) | Utvärderar det definierade uttryckets värde mot de definierade alternativa alternativen. Returnera resultatet av alternativet som är lika med värdet av uttrycket. Returnera annars det valfria standardresultatet, om ett sådant har angetts. (Standardresultatet är den sista parametern som inte föregås av ett alternativ.) | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")** returnerar strängen **"WINTER"** om det aktuella programsessionsdatumet är mellan oktober och december. Annars returneras en tom sträng. |
| IF (condition, value 1, value 2) | Returnera det första definierade värdet när det definierade villkoret uppfylls. Returnera annars det andra angivna värdet. Om värde 1 och värde 2 är poster eller postlistor, har resultatet enbart de fält som finns med i båda listorna. | **IF (1=2, "condition is met", "condition is not met")** returnerar strängen **"villkoret är inte uppfyllt"**. |
| NOT (condition) | Returnerar det omvända logiska värdet för det definierade kriteriet. | **NOT (SANT)** returnerar **FALSKT**. |
| OCH (villkor 1\[, villkor 2, …\]) | Returnerar **SANT** om *alla* definierade kriterier är sanna. Annars returneras **FALSKT**. | **AND (1=1, "a"="a")** returnerar **SANT**. **AND (1=2, "a"="a")** returnerar **FALSKT**. |
| ELLER (villkor 1\[, villkor 2, ...\]) | Returnerar **FALSKT** om *alla* definierade kriterier är falska. Returnerar **SANT** om *något* av de definierade kriterierna är sant. | **OR (1=2, "a"="a")** returnerar **SANT**. |
| VALUEIN (indata, lista, uttryck för listobjekt) | Bestämmer om specifik indata matchar något värde för ett objekt i den angivna listan. Returnerar **TRUE** om angiven indata matchar resultatet av det angivna uttrycket för minst en post. Annars returneras **FALSKT**. Parametern **indata** representerar sökvägen till ett datakällelement. Värdet för det här elementet kommer att matchas. Parametern **lista** representerar sökvägen till ett datakällelement av typ av postlista som en lista med poster som innehåller ett uttryck. Värdet för det här elementet ska jämföras med angiven indata. Argumentet **Uttryck för listobjekt** representerar ett uttryck som antingen refererar till eller innehåller ett enskilt fält för den angivna listan som ska användas för matchningen. | För exempel se avsnittet [Exempel: VALUEIN (indata, lista, uttryck för listobjekt)](#examples-valuein-input-list-list-item-expression) som följer. |

#### <a name="examples-valuein-input-list-list-item-expression"></a>Exempel: VALUEIN (indata, lista, uttryck för listobjekt)
I allmänhet översätts funktionen **VALUEIN** till en uppsättning **ELLER**-villkor:

(indata = list.item1.value) ELLER (indata = list.item2.value) ELLER...

##### <a name="example-1"></a>Exempel 1
Du kan definiera följande datakälla i din modellmappning: **lista** (**beräknat fält**-typ). Datakällan innehåller uttrycket **SPLIT ("a,b,c", ",")**.

När en datakälla anropas som konfigurerats som uttrycket **VALUEIN ("B", List, List.Value)** returnerar det **SANT**. I det här fallet översätts funktionen **VALUEIN** till följande uppsättning villkor:

**(("B" = "a") eller ("B" = "b") eller ("B" = "c"))**, där **("B" = "b")** är lika med **SANT**

När en datakälla anropas som konfigurerats som uttrycket **VALUEIN ("B", List, LEFT(List.Value, 0))** returnerar det **FALSKT**. I det här fallet översätts funktionen **VALUEIN** till följande villkor:

**("B" = "")**, vilket inte är lika med **SANT**

Observera att den övre gränsen för antalet tecken i texten i sådant tillstånd är 32 768 tecken. Därför bör du inte skapa datakällor som eventuellt överskrider begränsningen vid körning. Programmet ska sluta köras om gränsen överskrids och ett undantag genereras. Till exempel kan detta inträffa om datakällan har konfigurerats som **WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)** och listorna **List1** och **List2** innehåller en stor mängd poster.

I vissa fall kan funktionen **VALUEIN** översätts till en databas med hjälp av operatören **EXISTS JOIN**. Det här problemet uppstår när funktionen **FILTER** används och följande villkor uppfylls:

- Alternativet **FRÅGA EFTER FRÅGA** är inte markerat för datakällan för funktionen **VALUEIN** som refererar till listan över poster. (Inga ytterligare villkor ska kopplas till den här datakällan vid körning)
- Inga kapslade uttryck är konfigurerade för funktionen **VALUEIN** som refererar till listan över poster.
- Ett listobjekt för funktionen **VALUEIN** refererar till ett fält (inte ett uttryck eller en metod) i den angivna datakällan.

Överväg att använda det här alternativet i stället för funktionen **WHERE** som beskrivs tidigare i det här exemplet.

##### <a name="example-2"></a>Exempel 2

Du definierar följande datakällor i din modellmappning:

- **In** (typen **Registerposter**), som refererar till tabellen Intrastat
- **Port** (typen **Registerposter**), som refererar till tabellen IntrastatPort

När en datakälla anropas som konfigurerats som uttrycket **FILTER (In, VALUEIN(In.Port, Port, Port.PortId)** genereras följande SQL-sats för att returnera filtrerade poster i Intrastat-registret:

```
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

För fälten **dataAreaId** genereras den slutliga SQL-satsen utifrån operatör **IN**.

##### <a name="example-3"></a>Exempel 3

Du definierar följande datakällor i din modellmappning:

- **Le** (typen **beräknat fält**), som innehåller uttrycket **SPLIT ("DEMF,GBSI,USMF", ",")**
- **In** (typen **Registerposter**), som refererar till Intrastat-registret och för vilka alternativet **mellan företag** aktiveras

När en datakälla anropas som konfigurerats som den **FILTER (i VALUEIN (Le.Value In.dataAreaId Le,)**, slutgiltiga SQL-satsen innehåller följande villkor:

```
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

### <a name="mathematical-functions"></a>Matematiska funktioner

| Funktion | beskrivning | Exempel |
|----------|-------------|---------|
| ABS (number) | Returnera absolutvärdet av det angivna numret. (Med andra ord returnera tal utan tecken.) | **ABS (-1)** returnerar **1**. |
| POWER (number, power) | Returnerar resultatet av en ökning av det definierade positiva talet till den definierade kraften. | **POWER (10, 2)** returnerar **100**. |
| NUMBERVALUE (string, decimal separator, digit grouping separator) | Konverterar den definierade strängen till ett tal. Den angivna decimalavgränsaren används mellan heltal och decimaler i ett decimaltal. Den angivna gruppavgränsaren används som tusentalsavgränsare. | **NUMBERVALUE("1 234,56", ",", " ")** returnerar värdet **1234.56**. |
| VALUE (string) | Konverterar den definierade strängen till ett tal. Kommatecken och punkter (.) betraktas som decimalavgränsare och ett inledande bindestreck (-) används som ett negativt tecken. Meddela att ett undantag inträffat om den specificerade strängen innehåller andra icke-numeriska tecken. | **VALUE ("1 234,56")** kastar ett undantag. |
| ROUND (number, decimals) | Returnera det specificerade numret efter att det avrundats till det angivna antalet decimaler:<ul><li>Om värdet för parametern **decimaler** är större än 0 (noll) avrundas det specificerade numret till det angivna antalet decimaler.</li><li>Om värdet för parametern **decimaler** är **0** (noll) avrundas det specificerade numret till det angivna antalet decimaler.</li><li>Om värdet för parametern **decimaler** är mindre än 0 (noll) avrundas det specificerade numret till vänster om decimaltecknet.</li></ul> | **ROUND (1200.767, 2)** avrundar till två decimaler och returnerar **1200.77**. **ROUND (1200.767, -3)** avrundar till närmaste multipel av 1 000 och returnerar **1000**. |
| ROUNDDOWN (number, decimals) | Returnera det specificerade numret efter att det avrundats ned till det angivna antalet decimaler.<blockquote>[!NOTE] Den här funktionen fungerar som **ROUND** men avrundar alltid det specificerade numret nedåt (mot noll).</blockquote> | **ROUNDDOWN (1200.767, 2)** avrundar nedåt till två decimaler och returnerar **1200.76**. **ROUNDDOWN (1700.767, -3)** avrundar nedåt till närmaste multipel av 1 000 och returnerar **1000**. |
| ROUNDUP (number, decimals) | Returnera det specificerade numret efter att det avrundats upp till det angivna antalet decimaler.<blockquote>[!NOTE] Den här funktionen fungerar som **ROUND** men avrundar alltid det specificerade numret uppåt (från noll).</blockquote> | **ROUNDUP (1200.763, 2)** avrundar uppåt till två decimaler och returnerar **1200.77**. **ROUNDUP (1200.767, -3)** avrundar uppåt till närmaste multipel av 1 000 och returnerar **2000**. |

### <a name="data-conversion-functions"></a>Funktioner för datakonvertering

| Funktion | beskrivning | Exempel |
|----------|-------------|---------|
| VALUE (string) | Konverterar den definierade strängen till ett tal. Kommatecken och punkter (.) betraktas som decimalavgränsare och ett inledande bindestreck (-) används som ett negativt tecken. Meddela att ett undantag inträffat om den specificerade strängen innehåller andra icke-numeriska tecken. | **VALUE ("1 234,56")** kastar ett undantag. |
| NUMBERVALUE (string, decimal separator, digit grouping separator) | Konverterar den definierade strängen till ett tal. Den angivna decimalavgränsaren används mellan heltal och decimaler i ett decimaltal. Den angivna gruppavgränsaren används som tusentalsavgränsare. | **NUMBERVALUE("1 234,56", ",", " ")** returnerar **1234,56**. |
| INTVALUE (sträng) | Returnera en heltalsrepresentation av den specificerade strängen. Eventuella decimaler trunkeras. | **INTVALUE (”100.77”)** returnerar **100**. |
| INTVALUE (värde) | Returnera en heltalsrepresentation av det specificerade numret. Eventuella decimaler trunkeras. | **INTVALUE (-100.77)** returnerar **-100**. |
| INT64VALUE (string) | Returnera en int64 representation av den specificerade strängen. Eventuella decimaler trunkeras. | **INT64VALUE ("22565422744")** returnerar **22565422744**. |
| INT64VALUE (number) | Returnera en int64 representation av det specificerade numret. Eventuella decimaler trunkeras. | **INT64VALUE (22565422744.00)** returnerar **22565422744**. |

### <a name="record-functions"></a>Inspelningsfunktioner

| Funktion | beskrivning | Exempel |
|----------|-------------|---------|
| NULLCONTAINER (list) | Returnerar en **null**-post som har samma struktur som den definierade postlistan eller posten.<blockquote>[!NOTE] Den här funktionen är föråldrad. Använd **EMPTYRECORD** i stället.</blockquote> | **NULLCONTAINER (SPLIT ("abc", 1))** returnerar en ny tom post som har samma struktur som listan som returneras från **SPLIT**-funktionen. |
| EMPTYRECORD (record) | Returnerar en **null**-post som har samma struktur som den definierade postlistan eller posten.<blockquote>[!NOTE] En **noll** post är en post där alla fält innehåller ett tomt värde. Ett tomt värde är **0** (noll) för tal, en tom sträng för strängar, osv.</blockquote> | **EMPTYRECORD (SPLIT ("abc", 1))** returnerar en ny tom post som har samma struktur som listan som returneras från **SPLIT**-funktionen. |

### <a name="text-functions"></a>Textfunktioner

<table>
<thead>
<tr>
<th>Funktion</th>
<th>beskrivning</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr>
<td>UPPER (string)</td>
<td>Returnera den specificerade strängen efter att den konverterats till versaler.</td>
<td><strong>ÖVRE(&quot;prov&quot;)</strong> returnerar <strong>&quot;PROV&quot;</strong>.</td>
</tr>
<tr>
<td>LOWER (string)</td>
<td>Returnera den specificerade strängen efter att den konverterats till gemener.</td>
<td><strong>LÄGRE (&quot;Prov&quot;)</strong> returnerar <strong>&quot;prov&quot;</strong>.</td>
</tr>
<tr>
<td>LEFT (string, number of characters)</td>
<td>Returnerar det definierade antalet tecken från början av den definierade strängen.</td>
<td><strong>VÄNSTER (&quot;prov&quot;, 3)</strong> returnerar <strong>&quot;Pr&quot;</strong>.</td>
</tr>
<tr>
<td>RIGHT (string, number of characters)</td>
<td>Returnerar det definierade antalet tecken från slutet av den definierade strängen.</td>
<td><strong>HÖGER (&quot;Prov&quot;, 3)</strong> returnerar <strong>&quot;ov&quot;</strong>.</td>
</tr>
<tr>
<td>MID (string, starting position, number of characters)</td>
<td>Returnerar det definierade antalet tecken från den definierade strängen, med start från den definierade positionen.</td>
<td><strong>MEL (&quot;Prov&quot;, 2, 3)</strong> returnerar <strong>&quot;ro&quot;</strong>.</td>
</tr>
<tr>
<td>LEN (string)</td>
<td>Returnerar antalet tecken i den definierade strängen.</td>
<td><strong>LEN (&quot;Prov&quot;)</strong> returnerar <strong>6</strong>.</td>
</tr>
<tr>
<td>CHAR (number)</td>
<td>Returnerar teckensträngen som har en referens till det definierade Unicode-numret.</td>
<td><strong>CHAR (255)</strong> returnerar <strong>&quot;ÿ&quot;</strong>.
<blockquote>[!NOTE] Den sträng som returneras beror på viken kodning som har valts i det överordnade formatelementet FILE. För listan över vilka koder som stöds se <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Encoding class</a>.</blockquote>
</td>
</tr>
<tr>
<td>CONCATENATE (string 1 [, string 2, …])</td>
<td>Returnera alla specificerade textsträngar efter att de har sammanfogats till en sträng.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> returnerar <strong>&quot;abcdef&quot;</strong>.
<blockquote>[!NOTE] Uttrycket <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> returnerar också <strong>&quot;abcdef&quot;</strong>.</blockquote>
</td>
</tr>
<tr>
<td>ÖVERSÄTT (string, pattern, replacement)</td>
<td>Returnerar den definierade strängen efter att alla förekomster av tecknen i den definierade mönstersträngen har ersätts av tecknen på motsvarande position i den definierade utbytessträngen.</td>
<td><strong>ÖVERSÄTT (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> ersätter mönstret <strong>&quot;cd&quot;</strong> med strängen <strong>&quot;GH&quot;</strong> och returnerar <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr>
<td>REPLACE (string, pattern, replacement, regular expression flag)</td>
<td>Om flaggan för det definierade <strong>reguljära uttrycket</strong> har parametern <strong>sant</strong>, returneras den definierade strängen efter att ett reguljärt uttryck som definierats som ett <strong>mönsterargument</strong> för den här funktionen har tillämpats. Uttrycket används för att hitta tecken som måste ersättas. Tecknen i det definierade <strong>utbytesargumentet</strong> används för att ersätta tecken som hittas. Om flaggan för det definierade <strong>reguljära uttrycket</strong> har parametern <strong>falskt</strong>, uppför sig den här funktionen på samma sätt som <strong>ÖVERSÄTT</strong>.</td>
<td><strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, sant)</strong> tillämpar ett standarduttryck som avlägsnar alla icke-numeriska symboler och returnerar <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, falskt)</strong> ersätter mönstret <strong>&quot;cd&quot;</strong> med strängen <strong>&quot;GH&quot;</strong> och returnerar <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr>
<td>TEXT (input)</td>
<td>Returnera den specificerade indatan efter att den har konverteras till en textsträng formaterad enligt serverns lokala inställningar för den aktuella programinstansen. För värden av typen <strong>real</strong> är strängkonverteringen begränsad till två decimaler.</td>
<td>Om serverns lokala inställningar för Finance and Operations anges som <strong>EN-US</strong>, returnerar <strong>TEXT (NOW ())</strong> aktuellt datum för programsessionen, 17 december, 2015, som textsträngen <strong>&quot;2015-12-/17 07:59:23&quot;</strong>. <strong>TEXT (1/3)</strong> returnerar <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr>
<td>FORMAT (string 1, string 2[, string 3, …])</td>
<td>Returnera den definierade strängen efter att den har formaterats genom att byta ut alla förekomster av <strong>%N</strong> med argumentet <em>n</em>. Argumenten är strängar. Om ett argument inte har angetts för en parameter, returneras parametern som <strong>&quot;%N&quot;</strong> i strängen. För värden av typen <strong>real</strong> är strängkonverteringen begränsad till två decimaler.</td>
<td>I det här exemplet returnerar datakällan <strong>PaymentModel</strong> listan över kundposter via komponenten <strong>Customer</strong> och bearbetar datumvärdet via fältet <strong>ProcessingDate</strong>.
<p><a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a></p>
<p>I ER-formatet, som har utformats för att skapa en elektronisk fil för utvalda kunder, väljs <strong>PaymentModel</strong> som en datakälla och styr processflödet. Ett undantag meddelas användaren när en vald kund stoppas för det datum då rapporten bearbetas. Formeln, som utformats för denna typ av bearbetningsstyrning, kan endast använda följande resurser:</p>
<ul>
<li>Label SYS70894, som har följande text:
<ul>
<li><strong>För språket EN-US:</strong> &quot;Nothing to print&quot;</li>
<li><strong>För språket SV-SE:</strong> &quot;Inget att skriva ut&quot;</li>
</ul></li>
<li>Label SYS18389, som har följande text:
<ul>
<li><strong>För språket EN-US:</strong> &quot;Customer %1 is stopped for %2.&quot;</li>
<li><strong>För språket DE:</strong> &quot;Debitor '%1' wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
<p>Här följer formeln som kan utformas:</p>
<p>FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;))</p>
<p>Om en rapport bearbetas för kunden <strong>Litware-butikskund</strong> en 17 december 2015 i kulturen <strong>SV-SV</strong> och på språket <strong>SV-SV</strong>, kommer denna formel att returnera följande text som kan presenteras som ett undantagsmeddelande för slutanvändaren:</p>
<p>&quot;Inget att skriva ut. Customer Litware Retail is stopped for 12/17/2015."&quot;</p>
<p>Om samma rapport bearbetas för <strong>Litware-butikskunden</strong> den 17 december 2015, i kulturen <strong>DE</strong> och på språket <strong>DE</strong>, kommer denna formel att returnera följande text som använder ett annat datumformat:</p>
<p>&quot;Nichts zu drucken. Gäldenären 'Litware Butik' stoppad 2015-12-17.".&quot;</p>
<blockquote>[!NOTE] Följande syntax tillämpas i ER-formler för etiketter:
<ul>
<li><strong>För etiketter från Finance and Operations-programresurser:</strong> <strong>@&quot;X&quot;</strong>, där <strong>X</strong> är etikettens ID i programobjektträdet (Application Object Tree, AOT)</li>
<li><strong>För etiketter i ER-konfigurationer:</strong> <strong>@&quot;GER_LABEL:X&quot;</strong>, där <strong>X</strong> är etikettens ID i ER-konfigurationen</li>
</ul>
</blockquote>
</td>
</tr>
<tr>
<td>NUMBERFORMAT (number, format)</td>
<td>Returnera en sträng som representerar det specificerade numret i det angivna formatet. (Information om format som stöds finns i <a href="https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx">standard</a> och <a href="https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx">anpassade</a>.) Den kontext som denna funktion körs i avgör den kultur som används för att formatera tal.</td>
<td>För kulturen EN-US returnerar <strong>NUMBERFORMAT (0.45, &quot;p&quot;)</strong> <strong>&quot;45.00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> returnerar <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr>
<td>NUMBERFORMAT (number, format, kultur)</td>
<td>Returnera en sträng för det definierade nummer enligt angivet format och given kultur. (Om du vill ha mer information om format som stöds, se <a href="https://docs.microsoft.com/dotnet/standard/base-types/standard-numeric-format-strings">Standard</a> och <a href="https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings">Anpassat</a>.)</td>
<td><strong>NUMBERFORMAT (10/3, “F2”, "de")</strong> returnerar <strong>3,33</strong> medan <strong>NUMBERFORMAT (10/3, “F2”, "en-us")</strong> returnerar <strong>3.33</strong>.</td>
</tr>
<tr>
<td>NUMERALSTOTEXT (nummer, språk, valuta, skriv ut flagga för valutanamn, decimaler)</td>
<td>Returnera det specificerade numret efter att det har skrivits ut (konverterats) till textsträngar på det angivna språket. Språkkod är valfritt. När den är definierad som en tom sträng används istället språkkoden för löpande kontext. (Språkkoden för löpande kontext definieras för en skapande mapp eller fil.) Valutakoden är också valfri. När den definieras som en tom sträng, används företagsvalutan.
<blockquote>[!NOTE] Parametrarna för <strong>den utskrivna flaggan för valutanamn</strong> och <strong>decimalpunkter</strong> analyseras endast för följande språkkoder: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong>, och <strong>RU</strong>. I tillägg analyseras endast parametern <strong>utskriven flagga för valutanamn</strong> för företag vars länder eller regioner stöder valutanamnnedgång.</blockquote>
</td>
<td><strong>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2)</strong> returnerar <strong>&quot;One Thousand Two Hundred Thirty Four and 56&quot;</strong>. <strong>NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0)</strong> returnerar <strong>&quot;Sto dwadzieścia&quot;</strong>. <strong>NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2)</strong> returnerar <strong>&quot;Сто двадцать евро 21 евроцент&quot;</strong>.</td>
</tr>
<tr>
<td>PADLEFT (sträng, längd, teckenutfyllnad)</td>
<td>Returnera en sträng med angiven längd i de fall den aktuella strängens början är utfylld med de angivna tecknen.</td>
<td><strong>PADLEFT (&quot;1234&quot;, 10, &quot;&nbsp;&quot;)</strong> returnerar textsträngen <strong>&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234&quot;</strong>.</td>
</tr>
<tr>
<td>TRIM (string)</td>
<td>Returnera den angivna textsträngen efter att inledande och efterföljande blanksteg har trunkerats och multipla blanksteg mellan ord har tagits bort.</td>
<td><strong>TRIM (&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Sample&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;text&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&quot;)</strong> returnerar <strong>&quot;Sample text&quot;</strong>.</td>
</tr>
<tr>
<td>GETENUMVALUEBYNAME (uppräkning av sökväg för datakälla, uppräkning av etikettext för värde)</td>
<td>Returnera ett värde för den specificerade fasta datakällan baserat på den angivna texten för uppräkningsetiketten.</td>
<td>I följande illustration introduceras uppräkningen <strong>ReportDirection</strong> i en datamodell. Observera att etiketter definieras för uppräkningsvärden.
<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>Illustrationen som följer visar dessa detaljer:</p>
<ul>
<li>Modelluppräkningen <strong>ReportDirection</strong> infogas i en rapport som en datakälla <strong>$Direction</strong>.</li>
<li>ER-uttrycket <strong>$IsArrivals</strong> är utformat för att använda modelluppräkning som en parameter för denna funktion. Värdet för detta uttryck är <strong>TRUE</strong>.</li>
</ul>
<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>
</td>
</tr>
<tr>
<td>GUIDVALUE (indata)</td>
<td>Konvertera angivna indata för datatypen <strong>sträng</strong> till ett dataobjekt i datatypen <strong>GUID</strong>.<blockquote>[!NOTE] För att göra en konvertering i motsatt riktning (d.v.s. konvertera angiven indata för datatypen <strong>GUID</strong> till ett dataobjekt i datatypen <strong>sträng</strong>), kan du använda funktionen <strong>TEXT()</strong>.</blockquote></td>
<td>Du definierar följande datakällor i din modellmappning:
<ul>
<li><strong>myID</strong> (typen <strong>beräknat fält</strong>), som innehåller uttrycket <strong>GUIDVALUE (&quot;AF5CCDAC F728-4609-8C8B-A4B30B0C0AA0&quot;)</strong></li>
<li><strong>Användare</strong> (typen <strong>Registerposter</strong>), som refererar till tabellen UserInfo</li>
</ul>
När du har definierat dessa datakällor kan du använda ett uttryck såsom <strong>FILTER (Users, Users.objectId = myID)</strong> för att filtrera registret UserInfo genom <strong>objectId</strong> i datatypen <strong>GUID</strong>.
</td>
</tr>
<tr>
<td>JSONVALUE (id, sökväg)</td>
<td>Tolka data i JSON-format (JavaScript Object Notation) som används av den angivna sökvägen för att ta fram ett skalärvärde som baseras på angivet-ID.</td>
<td>Datakällan <strong>$JsonField</strong> innehåller följande data i JSON-format: <strong>{&quot;BuildNumber&quot;:&quot;7.3.1234.1&quot;, &quot;KeyThumbprint&quot;:&quot;7366E&quot;}</strong>. För den här datakällan returnerar </strong>JSONVALUE ( &quot;BuildNumber&quot;, $JsonField)</strong> värdet <strong>7.3.1234.1</strong> av datatypen <strong>sträng</strong>.</td>
</tr>
</tbody>
</table>

### <a name="data-conversion-functions"></a>Funktioner för datakonvertering

| Funktion | beskrivning | Exempel |
|----------|-------------|---------|
| TEXT (input) | Returnera den specificerade indatan efter att den har konverteras till en textsträng formaterad enligt serverns lokala inställningar för den aktuella programinstansen. För värden av typen **real** är strängkonverteringen begränsad till två decimaler. | Om serverns lokala inställningar för Finance and Operations anges som **EN-US**, returnerar **TEXT (NOW ())** aktuellt Finance and Operations-sessionsdatum, 17 December 2015, som textsträngen **"12/17/2015 07:59:23 AM"**. **TEXT (1/3)** returnerar **"0.33"**. |
| QRCODE (sträng) | Returnera en QR-kod (Quick Response Code ) i binärt base64-format för den specificerade strängen. | **QRCODE ("Sample text")** returnerar **U2FtcGxlIHRleHQ =**. |

### <a name="data-collection-functions"></a>Datainsamlingsfunktioner

| Funktion | beskrivning | Exempel |
|----------|-------------|---------|
| FORMATELEMENTNAME () | Returnera namnet på det aktuella formatets element. Returnera en tom sträng när flaggan **Samla in utdatadetaljer** är avstängd för aktuella filer. | Se uppgiftsguiden **ER Använd data från formatutmatningen för inventering och summering** (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner. |
| SUMIFS (nyckelsträng för summering, kriterispann1, kriterievärde1-sträng \[, kriteriespann2-sträng, kriterievärde2-sträng, …\]) | Returnera summan av värden som samlades in för XML-noder (där namnet definierats som en nyckel) när formatet kördes och som uppfyller angivna villkor (par med intervall och värden). Returnera ett **0** (noll) värde när flaggan **Samla in utdatadetaljer** i de aktuella filerna är avstängd. | |
| SUMIF (nyckelsträng för summering, sträng för kriteriespann, värdesträng för kriterier) | Returnera summan av värden som samlades in för XML-noder (där namnet definierats som en nyckel) när formatet kördes och som uppfyller det angivna villkoret (ett intervall och värde). Returnera ett **0** (noll) värde när flaggan **Samla in utdatadetaljer** i de aktuella filerna är avstängd. | |
| COUNTIFS (sträng för kriteriespann1, sträng för kriterievärde1 \[, sträng för kriteriespann2, sträng för kriterievärde2, …\]) | Returnerar antalet XML-noder som samlats in i när formatet kördes och som uppfyller de angivna villkoren (par med intervall och värden). Returnera ett **0** (noll) värde när flaggan **Samla in utdatadetaljer** i de aktuella filerna är avstängd. | |
| COUNTIF (intervallsträng för kriterier, värdesträng för kriterier) | Returnerar antalet XML-noder som samlats in i när formatet kördes och som uppfyller det angivna villkoret (ett intervall och värde). Returnera ett **0** (noll) värde när flaggan **Samla in utdatadetaljer** i de aktuella filerna är avstängd. | |
| COLLECTEDLIST (sträng för kriteriespann1, sträng för kriterievärde1 \[, sträng för kriteriespann2, sträng för kriterievärde2, …\]) | Returnerar listan över värden som samlats för XML-noder när formatet kördes och som uppfyller de angivna villkoren (ett intervall och värde). Returnera en tom lista när flaggan **Samla in utdatadetaljer** är avstängd för aktuella filer. | |

### <a name="other-business-domainspecific-functions"></a>Andra (företagsdomänspecifika) funktioner

| Funktion | beskrivning | Exempel |
|----------|-------------|---------|
| CONVERTCURRENCY (amount, source currency, target currency, date, company) | Konverterar det angivna penningbeloppet från den angivna källvalutan till den angivna målvalutan genom att använda inställningarna för det specificerade företaget på angivet datum. | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** returnerar motsvarigheten för en euro i US-dollar för det aktuella sessionsdatumet baserat på inställningarna för DEMF-företaget. |
| ROUNDAMOUNT (number, decimals, round rule) | Avrunda det angivna beloppet enligt den definierade avrundningsregeln och det angivna antalet decimaler.<blockquote>[!NOTE] Avrundningsregeln måste anges som ett värde för uppräkningen för **RoundOffType**.</blockquote> | Om parametern **model.RoundOff** anges som **Downward**, returnerar **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** värdet **1000.78**. Om **model.RoundOff**-parametern är inställd på **Normal** eller **Rounding-up** returnerar **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** värdet **1000.79**. |
| CURCredRef (digits) | Returnerar en betalningsmottagarreferens baserad på siffrorna i det angivna fakturanumret. | **CURCredRef ("VEND-200002")** returnerar **"2200002"**. |
| MOD\_97 (siffror) | Returnerar en betalningsmottagarreferens som ett MOD97-uttryck baserat på siffrorna i det angivna fakturanumret. | **MOD\_97 ("VEND-200002")** returnerar **"20000285"**. |
| ISOCredRef (digits) | Returnera en International Organization for Standardization (ISO)-betalningsmottagarreferens baserad på siffror och bokstäver i det angivna fakturanumret.<blockquote>[!NOTE] Om du vill ta bort symboler som inte överensstämmer med ISO-standarden från alfabetet måste indataparametern översättas innan den skickas till den här funktionen.</blockquote> | **ISOCredRef ("VEND-200002")** returnerar **"RF23VEND-200002"**. |
| CN\_GBT\_AdditionalDimensionID (sträng, nummer) | Hämta angiven ID för ytterligare ekonomisk dimension I parametern **sträng** representeras dimensioner som ID åtskilda med kommatecken. Parametern **nummer** definierar den begärda dimensionens seriekod i strängen. | **CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3)** returnerar **"CC"**. |
| GetCurrentCompany () | Returnera en textrepresentation av den kod för juridisk person (företag) som en användare för tillfället är inloggad till. | **GETCURRENTCOMPANY ()** returnerar **USMF** för en användare som är inloggad på företaget **Contoso Entertainment System USA**. |
| CH\_BANK\_MOD\_10 (siffror) | Returnera en betalningsmottagarreferens som ett MOD10-uttryck baserat på siffrorna i det angivna fakturanumret. | **CH\_BANK\_MOD\_10 ("VEND-200002")** returnerar **3**. |
| FA\_SUM (Anläggningstillgångskod, värdemodellkod, startdatum, slutdatum) | Returnera den förberedda databehållaren med anläggningstillgångsbelopp för angiven period. | **FA\_SUM ("COMP-000001", "Current", Date1, Date2)** returnerar den förberedda databehållaren för anläggningstillgången **"COMP-000001"** som har värdemodellen **"Current"** i en period mellan **Date1** och **Date2**. |
| FA\_BALANCE (Anläggningstillgångskod, värdemodellkod, rapporteringsår, rapporteringsdatum) | Returnera den förberedda databehållaren med anläggningstillgångssaldo. Rapporteringåret måste anges som ett värde på uppräkningen **AssetYear**. | **FA\_SUM ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())** returnerar den förberedda databehållaren för belopp tillhörande anläggningstillgången **"COMP-000001"** med värdemodellen **"Current"** på aktuellt programsessionsdatum. |
| TABLENAME2ID (string) | Returnera en heltalsrepresentation av ett register-ID för ett givet registernamn. | **TABLENAME2ID ("Intrastat")** returnerar **1510**. |
| ISVALIDCHARACTERISO7064 (string) | Returnerar booleskt värde **TRUE** när en specificerad sträng representerar ett giltigt internationellt bankkontonummer (IBAN). Annars returnera det booleska värdet **FALSE**. | **ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")** returnerar **SANT**. **ISVALIDCHARACTERISO7064 ("AT61")** returnerar **FALSKT**. |
| NUMSEQVALUE (nummerseriekod, område, områdes-ID) | Returnerar det nya genererade värdet för en nummerserie, utifrån angiven nummerseriekod, område och områdes-ID. Område måste anges som ett värde för uppräkningen **ERExpressionNumberSequenceområdes-IDType** (**delad**, **juridisk person** eller **företag**). För området **delad**, ange en tom sträng som områdes-ID. För området **företag** och **juridisk person**, ange företagskoden som områdes-ID. För området **företag** och **juridisk person**, om du anger en tom sträng som områdes-ID, används aktuella företagskoden. | Du definierar följande datakällor i din modellmappning:<ul><li>**enumScope** (typen **Dynamics 365 for Operations-uppräkning**) som hänvisar till uppräkningen **ERExpressionNumberSequenceScopeType**</li><li>**NumSeq** (typen **beräknat fält**), som innehåller uttrycket **NUMSEQVALUE (”Gene\_1”, enumScope.Company, ””)**</li></ul>När datakällan **NumSeq** kallas, returneras det nya genererade värdet för nummerserien **Gen\_1** som har konfigurerats för det företag som tillhandahåller den kontext som ER-formatet körs under. |
| NUMSEQVALUE (nummerseriekod) | Returnerar det nya genererade värdet för en nummerserie, baserat på den angivna nummerserien, området **företag** och koden för det företag som tillhandahåller kontexten som ER-formatet kör under (som områdes-ID). | Du kan definiera följande datakälla i din modellmappning: **NumSeq** (**beräknat fält**-typ). Datakällan innehåller uttrycket **NUMSEQVALUE ("Gene\_1")**. När datakällan **NumSeq** kallas, returneras det nya genererade värdet för nummerserien **Gen\_1** som har konfigurerats för det företag som tillhandahåller den kontext som ER-formatet körs under. |
| NUMSEQVALUE (nummerseriens post-ID) | Returnerar det nya genererade värdet för en nummerserie, utifrån angiven nummerseries post-ID. | Du definierar följande datakällor i din modellmappning:<ul><li>**LedgerParms** (**tabell** typ), som refererar till tabellen LedgerParameters</li><li>**NumSeq** (typen **beräknat fält**), som innehåller uttrycket **NUMSEQVALUE (LedgerParameters.'numRefJournalNum()'.NumberSequenceId)**</li></ul>När datakällan **NumSeq** kallas, returneras det nya genererade värdet för nummerserien som har konfigurerats i Redovisningsparametrar för det företag som tillhandahåller den kontext som ER-formatet körs under. Den här nummerserien identifierar unikt journaler och fungerar som ett batchnummer som kopplar ihop transaktionerna. |

### <a name="functions-list-extension"></a>Utöka funktionslista

ER stöder utökning av listfunktioner som används i ER-uttryck. Vissa tekniska insatser krävs. Om du vill ha mer information, se [Utöka listan över elektroniska rapporteringfunktioner](general-electronic-reporting-formulas-list-extension.md).

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Utöka listan över elektronisk rapportering (ER)](general-electronic-reporting-formulas-list-extension.md)