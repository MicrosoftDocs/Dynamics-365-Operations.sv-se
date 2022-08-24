---
title: Formelspråk i elektronisk rapportering
description: Den här artikeln innehåller information om hur du använder formelspråk i elektronisk rapportering (ER).
author: kfend
ms.date: 05/04/2020
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 7df29c74b2a430ed9d974cad709b975e4fd9cd35
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283296"
---
# <a name="electronic-reporting-formula-language"></a>Formelspråk i elektronisk rapportering

[!include [banner](../includes/banner.md)]

Elektronisk rapportering (ER) ger en kraftfull dataomvandlingserfarenhet. Det språk som används för att uttrycka nödvändiga datamanipuleringar i [ER-formeldesignern](general-electronic-reporting-formula-designer.md) liknar formelspråket i Microsoft Excel.

## <a name="basic-syntax"></a>Grundläggande syntax

ER-uttryck kan innehålla några eller flera av följande element:

- [Konstanter](#Constants)
- [Operatorer](#Operators)
- [Referenser](#References)
- [Sökvägar](#Paths)
- [Funktioner](#Functions)

## <a name="constants"></a><a name="Constants"></a>Konstanter

Du kan använda text och numeriska konstanter (värden som inte är beräknade) för att utforma uttryck. Till exempel uttrycket `VALUE ("100") + 20` använder den numeriska konstanten **20** och strängkonstanten **"100"** och returnerar det numeriska värdet **120**.

Elektronisk rapportering (ER) formeldesignern stöder escape-sekvenser. Därför kan du ange en uttryckssträng som ska hanteras på olika sätt. Uttrycket `"Leo Tolstoy ""War and Peace"" Volume 1"` returnerar till exempel textsträngen **Leo Tolstoy "krig och fred" volym 1**.

## <a name="operators"></a><a name="Operators"></a>Operatorer

Följande register visar de aritmetiska operatorer du kan använda för att göra grundläggande matematiska operationer såsom addition, subtraktion, multiplikation och division.

| Operatör | Betydelse               | Exempel     |
|----------|-----------------------|-------------|
| +        | Tillägg              | `1+2`       |
| -        | Subtraktion, negering | `5-2`, `-1` |
| \*       | Multiplikation        | `7\*8`      |
| /        | Indelning              | `9/3`       |

Följande tabell visar de jämförelseoperatorer som stöds. Du kan använda dessa operatorer för att jämföra två värden.

| Operatör | Betydelse                  | Exempel      |
|----------|--------------------------|--------------|
| =        | Lika                    | `X=Y`        |
| &gt;     | Större än             | `X>Y`        |
| &lt;     | Mindre än                | `X<Y`        |
| &gt;=    | Större än eller lika med | `X>=Y`       |
| &lt;=    | Mindre än eller lika med    | `X<=Y`       |
| &lt;&gt; | Inte lika med             | `X<>Y`       |

Dessutom kan du använda ett och-tecken (&) som en operator för textkonkatenering. På så sätt kan du koppla eller konkatenera en eller flera textsträngar till ett enda textstycke.

| Operatör | Betydelse     | Exempel                                               |
|----------|-------------|-------------------------------------------------------|
| &        | Sammanfoga | `"Nothing to print:" & " " & "no records found"`      |

### <a name="operator-precedence"></a>Operatorprioritet

Ordningen i vilken delarna i ett sammansatt uttryck utvärderas är viktig. Till exempel är det skillnad på resultatet av uttrycket `1 + 4 / 2` beroende på om additions- eller divisionsoperationen utförs först. Du kan använda parenteser för att explicit definiera hur ett uttryck utvärderas. Om du till exempel vill ange att additionsoperationen ska göras först kan du ändra det föregående uttrycket till `(1 + 4) / 2`. Om ordningen för operationer som ska utföras i ett uttryck inte uttryckligen rangordnas baseras ordningen på standardprioriteten som tilldelats de operatorer som stöds. Följande register visar den rangordning som tilldelats respektive operator. Operatorer som har en högre prioritet (till exempel 7) utvärderas före operatorer med en lägre prioritet (exempelvis 1).

| Prioritet | Operatorer      | Syntax                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Gruppering       | ( … )                                                                   |
| 6          | Medlemsåtkomst  | … . …                                                                   |
| 5          | Funktionsanrop  | … ( … )                                                                 |
| 4          | Multiplikation | … \* …<br>… / …                                                         |
| 3          | Additiv       | … + …<br>… - …                                                          |
| 2          | Jämförelse     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Separation     | … , …                                                                   |

Om ett uttryck omfattar flera på varandra följande operatorer med samma rangordning, utvärderas dessa åtgärder från vänster till höger. Exempelvis returnerar uttrycket `1 + 6 / 2 \* 3 > 5` **Sant**. Vi rekommenderar att du använder parenteser om du explicit vill ange önskad ordning för utvärdering av uttryck så att uttrycken blir enklare att läsa och underhålla.

## <a name="references"></a><a name="References"></a>Referenser

Alla datakällor för den aktuella ER-komponenten som är tillgängliga under utformningen av ett uttryck kan användas som namngivna referenser. Den aktuella ER-komponenten kan antingen vara en modellmappning eller ett format. Till exempel innehåller den aktuella ER-modellmappninge datakällan **ReportingDate**, som returnerar ett värde av datatypen [*DateTime*](er-formula-supported-data-types-primitive.md#datetime). I syfte att korrekt formatera värdet i skapande dokument kan du referera datakällan i uttrycket på följande sätt: `DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")`.

Alla tecken i referenser till en datakälla som inte representerar en bokstav i alfabetet måste föregås av en apostrof ('). Om namnet på en refererad datakälla innehåller minst en symbol som inte representerar inte en bokstav i alfabetet måste namnet visas inom enkla citattecken. Dessa icke-alfabetiska symboler kan till exempel vara skiljetecken eller andra skrivna symboler. Nedan följer några exempel:

- Datakällan **dagens datum och tid** måste refereras till i ett ER-uttryck som `'Today''s date & time'`.
- Metoden **name()** för datakällan **Kunder** måste refereras till i ett ER-uttryck som `Customers.'name()'`.

Om appdatakällor har parametrar måste följande syntax användas för att anropa dessa metoder:

- Om metoden **isLanguageRTL** för datakällan **System** har en **EN-US**-parameter av datatypen [*Sträng*](er-formula-supported-data-types-primitive.md#string) måste denna metod anges i ett ER-uttryck som `System.isLanguageRTL("EN-US")`.
- Det krävs inga citationstecken när ett metodnamn innehåller endast alfanumeriska symboler. Dock är de obligatoriska för en metod i en tabell när namnet innehåller parenteser.

När datakällan **System** läggs till en ER-mappning som refererar till programklassen **Global** returnerar uttrycket `System.isLanguageRTL("EN-US ")` ett *booleskt* värde **FALSK**. Det ändrade uttrycket `System.isLanguageRTL("AR")` returnerar det *booleska* värdet **SANT**.

Du kan begränsa hur värden skickas till parametrarna för den här typen av metod:

- Endast konstanter kan överföras till metoder av den här typen. Värdena för konstanterna definieras i designläge.
- Endast [primitiva](er-formula-supported-data-types-primitive.md) (basic) datatyper stöds för parametrar av detta slag. Primitiva datatyper är *Heltal*, *Realtal*, *Boolesk* och *Sträng*.

## <a name="paths"></a><a name="Paths"></a>Sökvägar

När ett uttryck refererar till en strukturerad datakälla kan du använda sökvägsdefinitionen för att välja ett specifikt primitivt element i den datakällan. En punkt (.) används för separera enskilda element i en strukturerad datakälla. Till exempel innehåller den aktuella ER-modellmappningen datakällan **InvoiceTransactions**, och denna returnerar en lista över poster. Poststrukturen **InvoiceTransactions** innehåller fälten **AmountDebit** och **AmountCredit**, som båda returnerar numeriska värden. Därför kan du designa följande uttryck för att beräkna det fakturerade beloppet: `InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit`. `InvoiceTransactions.AmountDebit` konstruktionen i det här uttrycket är den sökväg som används för att komma åt fältet **AmountDebit** i datakällan **InvoiceTransactions** för typen *postlista*.

### <a name="relative-path"></a>Relativ sökväg

Om sökvägen till en strukturerad datakälla börjar med ett "at"-tecken (@) är det en relativ sökväg. "At"-tecknet visas i stället för den återstående delen av den absoluta sökvägen till den hierarkiska trädstruktur som används. Illustrationen nedan visar ett exempel. Här anger den absoluta sökvägen `Ledger.'accountingCurrency()'` att redovisningsvalutavärdet från datakällan **redovisning** anges i fältet **AccountingCurrency** i datamodellen.

![Exempel på en absolut sökväg på sidan för ER-modellmappningsdesigner.](./media/ER-FormulaLanguage-AbsolutePath.png)

Exemplet i följande illustration visar hur en relativ sökväg används. Den relativa sökvägen `@.AccountNum` anger att fältet **AccountNum** för **Intrastat**-datakällan (som visas en nivå ovanför fältet **AccountNum** i datamodellens hierarkiska träd) används för att ange kund- eller leverantörskontonumret i datamodellens **AccountNum**-fält.

![Exempel på en relativ sökväg på sidan för ER-modellmappningsdesigner.](./media/ER-FormulaLanguage-RelativePath1.png)

Den återstående delen av den absoluta sökvägen visas också i [ER-formelredigeraren](general-electronic-reporting-formula-designer.md).

![Resterande del av den absoluta sökvägen på sidan för ER-formeldesigner.](./media/ER-FormulaLanguage-RelativePath2.png)

Mer information finns i [Använd en relativ sökväg i databindningar för ER-modeller och -format](relative-path-data-bindings-er-models-format.md).

## <a name="functions"></a><a name="Functions"></a>Funktioner

ER inbyggda funktioner kan användas i ER-uttryck. Alla datakällor i uttryckets sammanhang (aktuell ER-modellmappning eller aktuellt ER-format) kan användas som parametrar för anropsfunktioner i enlighet med listan över argument för anropsfunktionen. Konstanter kan också användas som parametrar av anropsfunktioner. Till exempel innehåller den aktuella ER-modellmappningen datakällan **InvoiceTransactions**, och denna returnerar en lista över poster. Poststrukturen **InvoiceTransactions** innehåller fälten **AmountDebit** och **AmountCredit**, som båda returnerar numeriska värden. Ett uttryck för att beräkna det fakturerade beloppet kan utformas på följande sätt med hjälp av den inbyggda ER-avrundningsfunktionen: `ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)`.

När du utformar ER-modellmappningar och ER-rapporter kan du använda ER-funktioner från följande kategorier:

- [Datum- och tidsfunktioner](er-functions-category-datetime.md)
- [Lista över funktioner](er-functions-category-list.md)
- [Logiska funktioner](er-functions-category-logical.md)
- [Matematiska funktioner](er-functions-category-mathematical.md)
- [Inspelningsfunktioner](er-functions-category-record.md)
- [Textfunktioner](er-functions-category-text.md)
- [Datainsamlingsfunktioner](er-functions-category-data-collection.md)
- [Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)
- [Funktioner för typkonvertering](er-functions-category-type-conversion.md)

## <a name="functions-list-extension"></a>Utöka funktionslista

ER stöder utökning av listfunktioner som används i ER-uttryck. Vissa tekniska insatser krävs. Om du vill ha mer information, se [Utöka listan över elektroniska rapporteringfunktioner (ER)](general-electronic-reporting-formulas-list-extension.md).

## <a name="compound-expressions"></a>Sammansatta uttryck

Du kan skapa sammansatta uttryck som använder funktioner från olika kategorier, förutsatt att datatyperna matchar. När du använder funktioner tillsammans matchar datatypen för utdata från en funktion till datatypen indata som krävs av en annan funktion. Om du till exempel vill undvika ett möjligt "List-is-Empty"-fel i en bindning av ett fält till ett ER-formatelement, kombinerar du funktioner från kategorin [Lista](er-functions-category-list.md) från kategorin [funktion](er-functions-category-logical.md) från den logiska kategorin, som visas i följande exempel. Här använder formeln funktionen [OM](er-functions-logical-if.md) för att testa om listan **IntrastatTotals** är tom innan den returnerar värdet för den aggregering som krävs från listan. Om **IntrastatTotals**-listan är tom returnerar formeln **0** (noll).

```vb
IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="multiple-solutions"></a>Flera lösningar

Du kan ofta få samma dataomvandlingsresultat på flera sätt, genom att använda funktioner från olika kategorier eller olika funktioner från samma kategori. Det föregående uttrycket kan till exempel också konfigureras med hjälp av funktionen [COUNT](er-functions-list-count.md) från [List](er-functions-category-list.md)-kategorin.

```vb
IF(COUNT (IntrastatTotals)=0, 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Utöka listan med funktioner för elektronisk rapportering](general-electronic-reporting-formulas-list-extension.md)

[Primitiva datatyper som stöds](er-formula-supported-data-types-primitive.md)

[Sammansatta datatyper som stöds](er-formula-supported-data-types-composite.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
