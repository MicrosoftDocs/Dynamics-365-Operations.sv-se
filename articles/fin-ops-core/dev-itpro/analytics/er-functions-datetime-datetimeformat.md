---
title: Funktionen DATETIMEFORMAT ER
description: Den här artikeln innehåller information om hur funktionen DATETIMEFORMAT elektronisk rapportering (ER) används.
author: kfend
ms.date: 09/08/2021
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
ms.openlocfilehash: e21b676046b6279826a728657fcc0d2a00a38b76
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287381"
---
# <a name="datetimeformat-er-function"></a>Funktionen DATETIMEFORMAT ER

[!include [banner](../includes/banner.md)]

Funktionen `DATETIMEFORMAT` returnerar ett värde för *[Sträng](er-formula-supported-data-types-primitive.md#string)* som visar ett givet datum/tidsvärde som text i angivet format och i en valfri angiven [kultur](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes). Om du vill ha mer information om format som stöds, se [Standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) och [Anpassat](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Syntax 1

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a>Syntax 2

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a>Argument

`datetime`: *[DatumTid](er-formula-supported-data-types-primitive.md#datetime)*

Ett datum-/tidsvärde som representerar det datum och den tid som ska formateras.

`format`: *Sträng*

Formatet på utdatasträngen Om du vill ha mer information om format som stöds, se [Standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) och [Anpassat](/dotnet/standard/base-types/custom-date-and-time-format-strings).

> [!NOTE]
> Formatsträngen är skiftlägeskänslig när du använder antingen ett standardformat eller ett anpassat format. Till exempel [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) "d" formatspecificeraren returnerar datumet med hjälp av det korta datummönstret, medan standard "D" formatspecificeraren returnerar datumet med hjälp av det långa datummönstret. Dessutom returnerar den [anpassade](/dotnet/standard/base-types/custom-date-and-time-format-strings) "M" formatspecificeraren månaden från 1 till 12, medan den anpassade "m" formatspecificeraren returnerar minuten från 0 till 59.

`culture`: *Sträng*

Kulturen som ska användas för formatering. För information om de kulturer som stöds, se [kultur](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande strängvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten. Om till exempel funktionen `DATETIMEFORMAT` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen. Standardvärdet `culture` är **EN-US**.

När `DATETIMEFORMAT`-funktionen konverterar ett givet datum/tidsvärde, beaktar den tidszonsinställningen för den programanvändare som kör det ER-format som funktionen anropas i kontexten för.

## <a name="example-1"></a>Exempel 1

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returnerar det aktuella datum/tidsvärdet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.

## <a name="example-2"></a>Exempel 2

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returnerar det aktuella datumet för programsessionen/tidsvärde, 24 december 2015 som **"2015-12-24"**, baserat på den valda tyska kulturen och det angivna formatet.

## <a name="example-3"></a>Exempel 3

`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returnerar strängvärdet **2019-11-12T08:00:00.0000000-08:00** när funktionen anropas under en process som initierades av en programanvändare som har tidszonsvärde **(GMT-08:00) Pacific Time (USA och Kanada)** i avsnittet **Språk och land/regionpreferenser**.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
