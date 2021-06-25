---
title: Primitiva datatyper som stöds för elektroniska rapporteringsformler
description: Detta ämne ger information om de primitiva datatyper som stöds i elektroniska rapporteringsformler (ER-formler).
author: NickSelin
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d5e6bb5e070ebbcdb7e99b1b70010acd5fca5ac
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "6224115"
---
# <a name="supported-primitive-data-types-for-electronic-reporting-formulas"></a>Primitiva datatyper som stöds för elektroniska rapporteringsformler

[!include [banner](../includes/banner.md)]

Detta ämne ger information om de primitiva datatyper som stöds i [elektroniska rapporteringsuttryck (ER-uttryck)](general-electronic-reporting.md). Här följer en lista primitiva datatyper:

- [boolesk](#boolean)
- [datum](#date)
- [datetime](#datetime)
- [uppräkning](#enumeration)
- [guid](#guid)
- [heltal](#integer)
- [int64](#int64)
- [real](#real)
- [sträng](#string)

## <a name="boolean"></a><a name="boolean"></a>Booleskt

Den *booleska* primitiva datatypen innehåller ett värde som utvärderas som antingen *sant* eller *falskt*. Du kan använda de reserverade bokstavliga nyckelorden **Sant** och **Falskt** varhelst ett *booleskt* uttryck förväntas. Standardvärdet är *falskt*.

Den interna representationen av *booleskt* är ett *heltal*. *Heltalsvärdet* 0 (noll) värderas som *falskt* och alla andra *heltalsvärden* värderas som *sanna*. När du [validerar](general-electronic-reporting-formula-designer.md#TestFormula) ett konfigurerat uttryck som returnerar en *boolesk* i [ER-formeldesignern](er-advanced-formula-editor.md) visas *0* (noll) i testresultatfönstret när ett uttryck returnerar *falskt*. Annars visas *1* i testresultatfönstret.

En *boolesk* har inga implicita omvandlingar. Du kan emellertid använda funktionen [TEXT](er-functions-text-text.md) för att uttryckligen konvertera en *boolesk* till en *sträng*:

- Det *falska* värdet konverteras till textsträngen **Falsk**.
- Det *falska* värdet konverteras till textsträngen **Sann**.

> [!NOTE]
> Denna abonnemangsändring beror inte på tillhandahållet språk- och kultur[sammanhang](er-design-multilingual-reports.md).

[Jämförelseoperatorer](er-formula-language.md#Operators) är den enda typen av operator som kan användas med den *booleska* datatypen. Följande operatorer kan användas för att jämföra två *booleska* värden: \<\> och =.

## <a name="date"></a><a name="date"></a>Datum

Den primitiva datatypen *datum* innehåller dag, månad och år. Datum kan initieras med hjälp av följande funktioner:

- [DATEVALUE](er-functions-datetime-datevalue.md)
- [NULLDATE](er-functions-datetime-nulldate.md)
- [SESSIONTODAY](er-functions-datetime-sessiontoday.md)
- [TODAY](er-functions-datetime-today.md)

Datumtypen *datum* kan innehålla datum mellan 1 januari 1900 och 31 december 2154. Standardvärdet är **null**, och den interna representationen är datumet 1 januari 1900.

Ett *datum* har inga implicita omvandlingar. Du kan emellertid använda följande explicita funktioner för omvandlingar:

- [DATEFORMAT](er-functions-datetime-dateformat.md)
- [DATETODATETIME](er-functions-datetime-datetodatetime.md)
- [TEXT](er-functions-text-text.md)

Med funktionen [ADDDAYS](er-functions-datetime-adddays.md) kan du lägga till och subtrahera dagar från datum. På så sätt kan du flytta datumet ett visst antal dagar in i framtiden och i det förflutna. Med funktionen [DAYS](er-functions-datetime-days.md) kan du subtrahera datum från varandra och beräkna skillnaden i dagar. Mer information om omvandlingen av *datumvärden* finns i [Lista över ER-funktioner i kategorin Datum och tid](er-functions-category-datetime.md).

[Jämförelseoperatorer](er-formula-language.md#Operators) är den enda typen av operator som kan användas med datatypen *datum*. Följande operatorer kan användas för att jämföra två värden för *datum*: \<\>, \<, \<=, =, \> och \>=.

## <a name="datetime"></a><a name="datetime"></a>DatumTid

Den primitiva datatypen *datetime* kombinerar typen *datum* och ett värde som representerar den tid som gått sedan midnatt. Tiden uttrycks i timmar, minuter, sekunder och bråkdelar av en sekund. Ett värde för *datetime* innehåller också information om tidszonen.

Datatypen *datetime* kan innehålla datum mellan den 1 januari 1900 (1900-01-01T00:00:00.0000000+00:00 i det fullständiga [formatet](/dotnet/standard/base-types/standard-date-and-time-format-strings)) och den 31 december 31 2154 (2154/12/31T11:59:59.9999999+00:00 i förlustfritt format). Den minsta tidsenheten i *datetime* är en tiomiljonsdel av en sekund.

> [!NOTE]
> När **hh** [specificeraren](/dotnet/standard/base-types/standard-date-and-time-format-strings) används för timmar kan inga tidsvärden som överstiger 12:59:59:9999999 tolkas som giltiga tidpunkter.
>
> När specificeraren **HH** används för timmar kan inga tidsvärden som överstiger 23:59:59:9999999 tolkas som giltiga tidpunkter.

Standardvärdet är **null** och den interna representationen är datumet 1 januari 1900 (1900-01-01T00:00:00.0000000+00:00 i förlustfritt format).

Datum kan initieras med hjälp av följande funktioner:

- [DATETIMEVALUE](er-functions-datetime-datetimevalue.md)
- [NULNULLDATETIMELDATE](er-functions-datetime-nulldatetime.md)
- [SESSIONNOW](er-functions-datetime-sessionnow.md)
- [NOW](er-functions-datetime-now.md)

Ett *datetime* har inga implicita omvandlingar. Du kan emellertid använda följande explicita funktioner för omvandlingar:

- [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [TEXT](er-functions-text-text.md)

Mer information om omvandlingen av värden för *datetime* finns i [Lista över ER-funktioner i kategorin Datum och tid](er-functions-category-datetime.md).

[Jämförelseoperatorer](er-formula-language.md#Operators) är den enda typen av operator som kan användas med datatypen *datetime*. Följande operatorer kan användas för att jämföra två värden för *datetime*: \<\>, \<, \<=, =, \> och \>=.

## <a name="enumeration"></a><a name="enumeration"></a>Uppräkning

Den primitiva datatypen *uppräkning* är en lista med exakta strängar. Du kan använda uppräkningar som har definierats i programmet [källkod](../dev-ref/xpp-data-primitive.md#enum). Du kan även presentera dina egna uppräkningar i ER-[datamodellen](general-electronic-reporting.md#data-model-and-model-mapping-components) och ER-[format](general-electronic-reporting.md#FormatComponentOutbound)komponenterna.

En *programuppräkning* kan användas i uttryck för valfri ER-modellmappning och valfritt ER-format.

I följande bild visas hur du kan lägga till uppräkningsmodellen **CustVendCorrecpreciReasonCode** i den redigerbara ER-datamodellen.

[![Konfigurera en modelluppräkning i ER-datamodelldesignern](./media/er-formula-supported-data-types-primitive-enum1.gif)](./media/er-formula-supported-data-types-primitive-enum1.gif)

En *modelluppräkning* kan användas i uttryck för valfri ER-modellmappning och valfritt ER-format som skapades under en datamodell där *uppräkningen* infördes.

I följande bild visas hur du kan lägga till uppräkningsformatet **Lista över underkategorier för återförda tillägg in natura** i det redigerbara ER-formatet.

[![Konfigurera en formatuppräkning i ER-formatdesignern](./media/er-formula-supported-data-types-primitive-enum2.gif)](./media/er-formula-supported-data-types-primitive-enum2.gif)

En *formatuppräkning* kan bara användas i uttryck för ER-formatet där *uppräkningen* införts.

Du måste använda lämplig typ av ER-datakällor för att ta med en specifik uppräkning till en konfigurerad ER-komponent som en konstant eller som ett värde som användaren som kör en ER-lösning definierat i dialogrutan vid körning.

- Programuppräkningar kan nås med datakällorna **Dynamics 365 for Operations \ Uppräkning** och **Allmänt \ Parametrar för användarindata**. I följande bild visas hur du i de redigerbara ER-formaten kan lägga till datakällorna **appenumNoYes** och **uipNoYes** som refererar till programuppräkningen **NoYes**.

    [![Lägga till datakällor för programuppräkning i ER-formatdesignern](./media/er-formula-supported-data-types-primitive-enum3a.gif)](./media/er-formula-supported-data-types-primitive-enum3a.gif)

- Du når uppräkningar för datamodeller med hjälp av datakällorna **Datamodell \ Uppräkning** och **Datamodell \ Inmatningsparametrar för uppräkningsanvändare**. I följande bild visas hur du i de redigerbara ER-formaten kan lägga till datakällan **CustVendCorrectiveReasonCode** som refererar till datamodelluppräkningen **CustVendCorrectiveReasonCode**.

    [![Lägga till datakällor för modelluppräkning i ER-formatdesignern](./media/er-formula-supported-data-types-primitive-enum3b.gif)](./media/er-formula-supported-data-types-primitive-enum3b.gif)

- Formatuppräkningar kan nås med datakällorna **Format \ Uppräkning** och **Format \ Inmatningsparametrar för uppräkningsanvändare**. I följande bild visas hur du i de redigerbara ER-formaten kan lägga till datakällan **NaturaReverseCharge** som refererar till formatuppräkningen **Underkategorier för återförda tillägg in natura**.

    [![Lägga till datakällor för formatuppräkning i ER-formatdesignern](./media/er-formula-supported-data-types-primitive-enum3c.gif)](./media/er-formula-supported-data-types-primitive-enum3c.gif)

En *uppräkning* har inga implicita omvandlingar. Du kan emellertid använda funktionen [TEXT](er-functions-text-text.md) för abonnemangsändring för att konvertera en *uppräkning* till en textsträng. Denna abonnemangsändring är inte språkberoende. För mer information om hur du kan associera ett värde för *uppräkning* med passande språkspecifika etiketter, se användningsexemplen för funktionerna [LISTOFFIELDS](er-functions-list-listoffields.md) och [GETENUMVALUEBYNAME](er-functions-text-getenumvaluebyname.md).

[Jämförelseoperatorer](er-formula-language.md#Operators) är den enda typen av operator som kan användas med datatypen *uppräkning*. Följande operatorer kan användas för att jämföra två *uppräknings*-värden: \<\> och =.

## <a name="guid"></a><a name="guid"></a>Guid

Den primitiva datatypen *guid* innehåller ett värde för globalt unik identifierare (GUID). Ett GUID är ett värde som kan användas i alla datorer och nätverk där en unik identifierare krävs. Det är osannolikt att numret kommer att dupliceras. En giltig GUID uppfyller alla följande specifikationer:

- Det måste finnas 32 hexadecimala siffror.
- Det måste dessutom finnas fyra strecksymboler som bäddas in på följande platser: 8-4-4-4-12.
- Dessutom kan valfria klamrar \{\} läggas till i början och slutet av strängen. Både **\{2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212\}** och **2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212** är giltiga GUID-strängar.
- Därför måste det finnas totalt 36 eller 38 tecken, beroende på om klamrar ska läggas till eller inte.
- De bokstäver som används som hexadecimala siffror kan vara versaler (A–F), gemener (a–f) eller blandade.

Följande explicita funktioner för omvandlingar kan användas:

- [GUIDVALUE](er-functions-text-guidvalue.md)
- [TEXT](er-functions-text-text.md)

[Jämförelseoperatorer](er-formula-language.md#Operators) är den enda typen av operator som kan användas med datatypen *guid*. Följande operatorer kan användas för att jämföra två *guid*-värden: \<\> och =.

## <a name="integer"></a><a name="integer"></a>Heltal

Den primitiva datatypen *Heltal* representerar ett tal som inte har några decimaler. Heltal används som kontrollvariabler i upprepade uttryck eller som index i postlistor.

En *heltal*-litteral är heltalet så som det angetts direkt i ett ER-[uttryck](general-electronic-reporting-formula-designer.md#formula-designer-overview) (en formel), till exempel **12345**. Ett *heltal* är 32 bitar stort. Standardvärdet är **0**, och den interna representationen är ett långt nummer. Ett *heltal* konverteras automatiskt till en *real*.

Följande explicita funktioner för omvandlingar kan dessutom användas:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

Intervallet för ett *heltal* är \[-2,147,483,647 : 2,147,483,647\]. Alla heltal i det här intervallet kan användas som exakta tal.

Alla jämförelse- och matematiska [operatorer](er-formula-language.md#Operators) kan användas med datatypen *heltal*.

## <a name="int64"></a><a name="int64"></a>Int64

Den primitiva datatypen *int64* representerar ett tal som inte har några decimaler. *Int64*-värden används som kontrollvariabler i upprepade uttryck eller som postidentifierare.

Ett *in64* är 64 bitar stort. Standardvärdet är **0**, och den interna representationen är ett långt nummer. Ett *int64* konverteras automatiskt till en *real*.

Följande explicita funktioner för omvandlingar kan dessutom användas:

- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

Intervallet för ett *int64* är \[-9,223,372,036,854,775,807 : 9,223,372,036,854,775,807\].

Alla jämförelse- och matematiska [operatorer](er-formula-language.md#Operators) kan användas med datatypen *int64*.

## <a name="real"></a><a name="real"></a>Realtal

Den primitiva datatypen *real* kan förutom heltal även innehålla decimalvärden. Du kan använda decimalheltal var som helst där en *real* förväntas. Ett decimaltal är det decimaltal som anges direkt i koden, till exempel **2,19**.

> [!NOTE]
> I ER-uttryck används alltid en punkt (.) som decimalavgränsare.

Realer kan användas i alla uttryck och kan användas med både jämförelse- och aritmetiska operatorer. En *real* har en precision på 16 signifikanta siffror. Standardvärdet för en *real* är **0,0**, och den interna representationen är ett binärkodat digitalt nummer (BCD). BCD-kodningen gör det möjligt att exakt representera värden som är multiplar av 0,1. Intervallet för en *real*-variabel är -(10)<sup>127</sup> genom (10)<sup>127</sup>. Alla realer i det här intervallet kan användas som exakta tecken i ER-uttryck.

En *real* har inga implicita omvandlingar. Du kan emellertid använda följande funktioner om du explicit vill konvertera en *real* till andra datatyper och andra datatyper till en *real*:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)
- [VALUE](er-functions-conversion-value.md)

Alla jämförelse- och matematiska [operatorer](er-formula-language.md#Operators) kan användas med datatypen *real*.

## <a name="string"></a><a name="string"></a>Sträng

Den primitiva datatypen *sträng* representerar en serie tecken som används som texter, kontonummer, adresser och telefonnummer.

Exakta *Sträng*-tecken är tecken som omges av citattecken (""). Exakta *Sträng*-tecken kan användas där *strängvärden* förväntas i ER-uttryck. Du kan använda strängar i logiska uttryck, till exempel jämförelser. Du kan också använda *sträng*-värden genom att använda operatorn **\&** eller funktionen [CONCATENATE](er-functions-text-concatenate.md).

> [!NOTE]
> Om du sammanfogar två *sträng* värden och vill att den resulterande *strängen* ska sträcka sig över mer än en rad använder du radbrytningsavgränsaren mellan värdena. För TEXT-utdata kan den här avgränsaren vara ett tecken som genereras med hjälp av uttrycket [CHAR](er-functions-text-char.md)(10) eller CHAR(13). För HTML kan det vara **\<br\>**-taggen.

Standardvärdet för en *sträng* är en tom textsträng utan tecken, och den interna representationen är en teckenlista.

Det finns inga automatiska omvandlingar för strängar. Följande explicita omvandlingsfunktioner kan emellertid användas:

- [CHAR](er-functions-text-char.md)
- [FORMAT](er-functions-text-format.md)
- [LEFT](er-functions-text-left.md)
- [LEN](er-functions-text-len.md)
- [MID](er-functions-text-mid.md)
- [PADLEFT](er-functions-text-padleft.md)
- [REPLACE](er-functions-text-replace.md)
- [RIGHT](er-functions-text-right.md)
- [TEXT](er-functions-text-text.md)
- [TRANSLATE](er-functions-text-translate.md)
- [TRIM](er-functions-text-trim.md)
- [UPPER](er-functions-text-upper.md)

Mer information om omvandlingen av *sträng*-värden finns i [Lista över ER-funktioner för textkategorin](er-functions-category-text.md).

En *sträng* kan innehålla ett oändligt antal tecken.

Alla jämförelse [operatorer](er-formula-language.md#Operators) kan användas tillsammand med datatypen *sträng*.

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Formelspråk i elektronisk rapportering](er-formula-language.md)
- [Sammansatta datatyper som stöds](er-formula-supported-data-types-composite.md)
