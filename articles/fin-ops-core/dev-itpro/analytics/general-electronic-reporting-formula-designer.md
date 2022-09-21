---
title: Formeldesigner i elektronisk rapportering (ER)
description: Den här artikeln innehåller information om hur du använder formeldesignern i elektronisk rapportering (ER).
author: kfend
ms.date: 04/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 283c882300ece460c18ffebe572238e7629f8dee
ms.sourcegitcommit: a1d14836b40cfc556f045c6a0d2b4cc71064a6af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2022
ms.locfileid: "9476823"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>Formeldesigner i elektronisk rapportering (ER)

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information om hur du använder formeldesignern i Elektronisk rapportering (ER). Om du utformar ett format för ett visst elektroniskt dokument i ER kan du använda formler för datatransformering för att uppfylla kraven för dokumentets uppfyllelse och formatering. Dessa formler liknar formler i Microsoft Excel. Formulären ger stöd åt olika typer av funktioner: text, datum och tid, matematik, logik, information, funktioner för datatypskonvertering och andra (företagsdomänspecifika funktioner).

## <a name="formula-designer-overview"></a>Formel designer översikt

ER stöder formeldesignern. Därför kan du vid designtillfället konfigurera uttryck som kan användas för följande uppgifter under körning:

- Omvandla data som tas emot från en appdatabas och som anges i en ER-datamodell som fungerar som datakälla för ER-format. (Till exempel kan dessa omvandlingar omfatta konvertering, filtrering och gruppering av datatyp.)
- Formatera data som ska skickas till ett skapande elektroniskt dokument i enlighet med layout och villkor för ett specifikt ER-format. (Till exempel kan formateringen göras i enlighet med det begärda språket eller kulturen, eller i enlighet med kodning).
- Kontrollera processen för generering av elektroniska dokument. (Till exempel kan uttryck aktivera eller inaktivera utdata från specifika element av formatet, beroende på bearbetade data. De kan också avbryta processen att skapa dokument eller skicka meddelanden till användare.)

Du kan öppna sidan **Formula designer** när du utför någon av följande åtgärder:

- Binda datakällsartiklar till datamodellkomponenter.
- Binda datakällsartiklar till formatkomponenter
- Slutför underhåll av beräknade fält som är en del av datakällor.
- Definiera synlighets- och redigerbarhetsvillkoren för användarnas indataparametrar.
- Definiera standardvärden för användarnas indataparametrar.
- Utforma transformeringar för ett format.
- Definiera aktiveringsvillkoren för formatets komponenter.
- Definiera filnamnen för formatets FIL-komponenter.
- Definiera villkoren för processtyrningsvalideringarna.
- Definiera meddelandetexten för processtyrningsvalideringar.

## <a name="data-binding"></a><a name="Binding"></a>Data bindande

ER-formeldesignern kan användas för att definiera ett uttryck som transformerar data som tagits emot från datakällor så att dessa data kan anges i datakonsumenten vid körning på följande sätt:

- Från appdatakällor och körtidsparametrar till en ER-datamodell
- Från en ER-datamodell till ett ER-format
- Från appdatakällor och körtidsparametrar till en ER-format

Bilden visar hur ett uttryck av den här typen skapas. I det här exemplet avrundar uttrycket värdet i fältet **Intrastat.AmountMST** i tabellen Intrastat till två decimaler och returnerar det avrundade värdet.

[![Databindningsuttryck.](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

Bilden nedan visar hur ett uttryck av den här typen kan användas. I det här exemplet anges resultatet av det utformade uttrycket i komponenten **Transaction.InvoicedAmount** i datamodellen **Tax reporting model**.

[![Databindningsuttryck som används.](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

Vid körning avrundar den designade formeln `ROUND (Intrastat.AmountMST, 2)` värdet av fältet **AmountMST** för varje post i tabellen Intrastat till två decimaler. Därefter skrivs det avrundade värdet in i komponenten **Transaction.InvoicedAmount** i datamodellen **Tax reporting**.

## <a name="data-formatting"></a><a name="Transformation"></a>Data formatering

ER-formeldesignern kan användas för att definiera uttryck som formaterar data som tagits emot från datakällor, så att dessa data kan skickas som en del av det skapade elektroniska dokumentet. Du har kanske en formatering som måste användas som en typisk regel och som ska återanvändas för ett format. Då kan du ange den formateringen en gång för alla i formatkonfigurationen, som en namngiven omvandling som innehåller ett uttryck med formatering. Den namngivna transformeringen kan sedan länkas till flera formatkomponenter, där utdata måste vara formaterade enligt det uttryck du skapade.

Bilden nedan visar hur du skapar en transformering av den här typen. I det här exemplet trunkerar **TrimmedString**-transformeringen inkommande data för datatypen *String* genom att ta bort inledande och avslutande blanksteg. Därefter returneras det trunkerade strängvärdet.

[![Omvandling.](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

Bilden nedan visar hur en transformering av den här typen kan användas. I det här exemplet skickar flera formatkomponenter text som utdata till det skapande elektroniska dokumentet vid körning. Dessa formatkomponenter hänvisar till **TrimmedString**-transformationen med namn.

[![Omvandling som används.](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

När formatkomponenter, såsom komponenten **partyName** i föregående illustration, hänvisar till transformeringen **TrimmedString** sänds text som utdata till det skapande elektroniska dokumentet. Denna text inkluderar inte inledande eller avslutande blanksteg.

Om du har en formatering som måste tillämpas separat kan du införa den formateringen som ett individuellt uttryck för en bindning av en särskild formatkomponent. Bilden visar ett uttryck av den här typen. I det här exemplet är **partyType**-formatkomponenten bunden till datakällan via ett uttryck som omvandlar inkommande data från fältet **Model.Company.RegistrationType** i datakällan till versal text. Uttrycket skickar sedan texten som utdata till det elektroniska dokumentet.

[![Tillämpa formatering på en enskild komponent.](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

## <a name="process-flow-control"></a><a name="Validation"></a>Processen flödeskontroll

ER-formeldesignern kan användas för att definiera uttryck som styr processflödet för skapande elektroniska dokument. Du kan utföra följande uppgifter:

- Definiera villkor som fastställer när processen för att skapa ett dokument måste stoppas.
- Definiera uttryck som antingen skapar meddelanden till användaren om stoppade processer eller sänder körningsloggmeddelanden om den pågående processen att skapa en rapport.
- Definiera filnamnen på de skapande elektroniska dokumenten och styr villkoren för hur de skapas.

Varje regel i processen flödeskontroll är utformad som en individuell validering. Bilden nedan visar en validering av den här typen. Här följer en förklaring av konfigureringen i det här exemplet:

- Valideringen utvärderas när **INSTAT**-noden skapas under generering av XML-filen.
- Valideringen stoppar körningsprocessen och returnerar **FALSKT** om listan över transaktioner är tom.
- Valideringen returnerar ett felmeddelande som innehåller texten i etiketten SYS70894 på användarens valda språk.

[![Validering.](./media/picture-validation.jpg)](./media/picture-validation.jpg)

ER-formeldesignern kan även användas för att skapa ett filnamn för ett skapande elektroniskt dokument och styra processen för hur en fil skapas. Bilden nedan visar utformningen av en styrning av ett processflöde av den här typen. Här följer en förklaring av konfigureringen i det här exemplet:

- Listan med poster från datakällan **modell. Intrastat-** är uppdelat i batchar. Varje batch innehåller upp till 1 000 poster.
- Utdata skapar en zip-fil som innehåller en fil i XML-format för varje skapad batch.
- Ett uttryck returnerar ett filnamn för skapande elektroniska dokument genom att konkatenera filnamnet och filnamnstillägget. För den andra batchen och alla efterföljande batchar innehåller filnamnet batchens ID som ett suffix.
- Ett uttryck möjliggör (genom att returnera **TRUE**) processen för att skapa en fil för batchar som innehåller minst en post.

[![Processflödeskontroll.](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

## <a name="document-content-control"></a><a name="Enabled"></a>Kontroll av dokumentinnehåll

Du kan använda ER-formuldesigner för att konfigurera uttryck som styr vilka data som ska placeras i genererade elektroniska dokument vid körning. Till exempel kan uttryck aktivera eller inaktivera utdata från specifika element av formatet, beroende på bearbetade data och konfigurerad logik. Uttrycken kan anges för ett enskilt formatelement i fältet **Aktiverad** på fliken **Mappning** på sidan **Operations designer**. Du kan ange uttrycken som ett logiskt villkor som returnerar ett *booleskt* värde:

- Om villkoret returnerar **Sant** körs det aktuella formatelementet.
- Om villkoret returnerar **Falskt** hoppas det aktuella formatelementet över.

Bilden visar uttryck av den här typen. (Version 11.12.11 av **ISO20022 kreditöverföring (NO)** formatkonfiguration som tillhandahålls av Microsoft används som ett exempel.) **XMLHeader**-formatkomponenten är konfigurerad för att beskriva strukturen för kreditöverföringsmeddelandet enligt ISO 20022 XML-meddelandestandarderna. Formatkomponenten **XMLHeader/dokument/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/ Ustrd** är konfigurerad för att lägga till det genererade meddelandet, XML-elementet **Ustrd** och lägga remitteringsinformationen i en ostrukturerat format som text i följande XML-element:

- **PaymentNotes**-komponenten används för att skapa texten i betalningsanteckningarna.
- **DelimitedSequence**-komponenten genererar kommaavgränsade fakturanummer som används för att kvitta den aktuella kreditöverföringen.

[![Komponenterna PaymentNotes och DelimitedSequence.](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> **PaymentNotes**- och **DelimitedSequence**-komponenterna märks med hjälp av ett frågetecken. Ett frågetecken indikerar att användningen av en komponent är villkorad. I det här fallet baseras användningen av komponenterna på följande kriterier:
>
> - Uttrycket `@.PaymentsNotes <> ""` som definieras för komponenten **PaymentNotes** aktiverar (genom att returnera **SANT**) **Ustrd** XML-element att fyllas i med text av betalningsanteckningar om den texten inte är tom för den aktuella kreditöverföringen.
>
>    [![Uttryck för komponenten PaymentNotes.](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)
>
> - Uttrycket `@.PaymentsNotes = ""` som definieras för komponenten **DelimitedSequence** aktiverar (genom att returnera **SANT**) **Ustrd** XML-elementet att fyllas i med en kommaseparerad lista av de fakturanummer som används för att kvitta den aktuella kreditöverföringen när texten för betalningsnoteringar om kreditöverföringen är tom.
>
>    [![Uttryck för komponenten DelimitedSequence.](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)
> 
> Baserat på denna inställning, meddelandet som genereras för varje gäldenärsbetalning, **Ustrd** XML-element, som antingen innehåller texten på betalningsanteckningar eller om den texten är tom, en kommaseparerad lista av de fakturanummer som används för att kvitta betalningen.

## <a name="assistance-in-formulas-writing"></a>Hjälp med att skriva formel

### <a name="data-sources-navigator"></a>Datakällor navigator

Du kan redigera en formel som representerar ett element i en strukturerad datakälla. När du konfigurerat ER-parametrarna så att sökvägen till ett element i en strukturerad datakälla som [relativ sökvägar](relative-path-data-bindings-er-models-format.md), "at" (@) tecken [visa](er-formula-language.md#relative-path) i formeln istället för den återstående delen av den absoluta sökvägen för den hierarkiska trädstrukturen som används. Denna återstående del av den absoluta sökvägen pekar på ett överordnat element till den redigerbara. I Ekonomi version **10.0.30 och senare**, på sidan **Formeldesigner** i rutan **Datakällor** kan du välja alternativet **Go to @** för att placera markören för datakällträdet till ett element som är föräldern till det redigerbara. Strukturen för alla komprimerade stigande element expanderas automatiskt och rekursivt vid behov. Den här expansionen kan hjälpa dig att snabbt visualisera baselementet i det redigerbara elementet, iaktta underordnade moduler av det redigerbara elementet i datakällträdet och använda var och en av dem i den redigerbara formeln om det behövs.

![Använd alternativet "Gå till @" om du vill placera markören för datakällorna i ett element som är överordnat det redigerbara elementet på sidan Formeldesigner.](./media/er_formula-designer-data-sources-navigator.gif)

### <a name="data-sources-picker"></a>Datakälla väljare

På sidan **Formeldesigner** i rutan **Datakällor** till vänster, välj ett element i en datakälla som du vill ta med till den redigerbara formeln. Välj **Lägg till datakälla**. Lägg märke till att det valda elementet läggs till i texten i den redigerbara formeln.

> [!TIP]
> När du använder alternativet **Lägg till datakälla** i standardformelredigeraren läggs det valda elementet alltid till i slutet av formeltexten. När du gör samma sak i [redigeraren för avancerad formel](er-advanced-formula-editor.md) infogas det valda elementet i formeltexten vid den aktuella markörpositionen.

### <a name="built-in-functions-picker"></a>Inbyggda funktionsväljare

På sidan **Formeldesigner** i rutan **Funktioner** till höger, välj ett element i en ER inbyggda funktioner som du vill ta med till den redigerbara formeln. Välj **Lägg till funktion**. Lägg märke till att det valda funktion läggs till i texten i den redigerbara formeln.

> [!TIP]
> När du använder alternativet **Lägg till funktion** i standardformelredigeraren läggs den valda funktionen alltid till i slutet av formeltexten. När du gör samma sak i [redigeraren för avancerad formel](er-advanced-formula-editor.md) infogas den valda funktion i formeltexten vid den aktuella markörpositionen.

### <a name="validation-of-configured-formulas"></a><a name="TestFormula"></a>Validering av konfigurerade formler

På sidan **formeldesignern** väljer du **test** för att validera hur den konfigurerade formeln fungerar.

[![Välja Test för att validera en formel.](./media/ER-FormulaTest-Start.png)](./media/ER-FormulaTest-Start.png)

När värdena för formelargument krävs kan du öppna dialogrutan **Testuttryck** från sidan **Formulärdesigner**. I de flesta fall måste dessa argument definieras manuellt, eftersom de konfigurerade bindningarna inte körs vid designtillfället. Fliken **testresultat** på sidan **formeldesigner** visar resultatet från körningen av den konfigurerade formeln.

I följande exempel visas hur du kan testa formeln som har konfigurerats för den utländska handels domänen att kontrollera att Intrastat-artikelkoden innehåller endast siffror.

När du testar den här formeln kan du använda dialogrutan **testuttryck** för att ange värdet för Intrastat-varukoden för testning.

[![Ange Intrastat-varukoden för testning.](./media/ER-FormulaTest-Start-EnterArguments.png)](./media/ER-FormulaTest-Start-EnterArguments.png)

När du har angett Intrastat-artikelkoden och väljer **OK**, visar fliken **Testresultat** på sidan **Formeldesigner** resultatet av körningen av den konfigurerade formeln. Du kan sedan utvärdera om resultatet är acceptabelt. Om resultatet inte är acceptabelt kan du uppdatera formeln och testa den igen.

[![Testresultat.](./media/ER-FormulaTest-Result.png)](./media/ER-FormulaTest-Result.png)

Vissa formler kan inte testas vid designtillfället. En formel kan till exempel returnera ett resultat av en datatyp som inte kan visas på fliken **testresultat**. I det här fallet visas ett felmeddelande som säger att formeln inte kan testas.

[![Felmeddelande.](./media/ER-FormulaTest-Error.png)](./media/ER-FormulaTest-Error.png)

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Formelspråk i elektronisk rapportering](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
