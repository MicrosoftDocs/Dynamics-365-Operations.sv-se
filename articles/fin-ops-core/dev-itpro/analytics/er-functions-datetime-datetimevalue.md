---
title: Funktionen DATETIMEVALUE ER
description: Den här artikeln innehåller information om hur funktionen DATETIMEVALUE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 591c707ae7f57236386de0b4ef85d428c9ae31fd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287351"
---
# <a name="datetimevalue-er-function"></a>Funktionen DATETIMEVALUE ER

[!include [banner](../includes/banner.md)]

Funktionen `DATETIMEVALUE` returnerar ett värde för *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* som konverteras från ett givet textvärde i angivet format och i en valfri angiven [kultur](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes). Om du vill ha mer information om format som stöds, se [Standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) och [Anpassat](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Syntax 1

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a>Syntax 2

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argument

`text`: *[Sträng](er-formula-supported-data-types-primitive.md#string)*

Text som representerar värdet till format.

`format`: *Sträng*

Formatet för en given text. Om du vill ha mer information om format som stöds, se [Standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) och [Anpassat](/dotnet/standard/base-types/custom-date-and-time-format-strings).

`culture`: *Sträng*

Den kultur som används för att formatera den givna texten. För information om de kulturer som stöds, se [kultur](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Returvärden

*DatumTid*

Det resulterande datum/tid-värdet.

## <a name="usage-notes"></a>Användningsanteckningar

När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten. Om till exempel funktionen `DATETIMEVALUE` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen. Standardvärdet `culture` är **EN-US**.

## <a name="example-1"></a>Exempel 1

`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returnerar **2:55:00 är den 21 december 2016**, baserat på det angivna anpassade formatet och standardprogrammets **EN-US**-kultur.

## <a name="example-2"></a>Exempel 2

`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returnerar **2:55:00 på 21 december 2016**, baserat på det angivna anpassade formatet och kulturen.

Men `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` ska utlösa ett undantag som informerar användaren om att den angivna strängen inte identifieras som ett datum/tidsvärde för den angivna kulturen.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
