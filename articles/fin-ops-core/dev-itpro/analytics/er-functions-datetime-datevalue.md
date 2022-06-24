---
title: DATEVALUE ER-funktion
description: Den här artikeln innehåller information om hur funktionen DATEVALUE elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 09/08/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 396d6823531d8bf2c5b5f61f2483422c84e54c62
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883800"
---
# <a name="datevalue-er-function"></a>DATEVALUE ER-funktion

[!include [banner](../includes/banner.md)]

Funktionen `DATEVALUE` returnerar ett värde för *[Datum](er-formula-supported-data-types-primitive.md#date)* som konverteras från ett givet textvärde i angivet format och i en valfri angiven [kultur](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) till ett datumvärde. Om du vill ha mer information om format som stöds, se [Standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) och [Anpassat](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Syntax 1

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a>Syntax 2

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argument

`text`: *[Sträng](er-formula-supported-data-types-primitive.md#string)*

Text som representerar värdet till format.

`format`: *Sträng*

Formatet för en given text. Om du vill ha mer information om format som stöds, se [Standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) och [Anpassat](/dotnet/standard/base-types/custom-date-and-time-format-strings).

`culture`: *Sträng*

Den kultur som används för att formatera den givna texten. För information om de kulturer som stöds, se [kultur](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Returvärden

*Datum*

Det resulterande datum-värdet.

## <a name="usage-notes"></a>Användningsanteckningar

När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten. Om till exempel funktionen `DATEVALUE` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen. Standardvärdet `culture` är **EN-US**.

## <a name="example-1"></a>Exempel 1

`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returnerar datumvärdet **21 december 2016**, baserat på det angivna anpassade formatet och standardprogrammets **EN-US**-kultur.

## <a name="example-2"></a>Exempel 2

`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returnerar datumvärdet **21 januari 2016**, baserat på angivet anpassat format och kultur.

Men `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` ska utlösa ett undantag som informerar användaren om att den angivna strängen inte identifieras som ett datum för den angivna kulturen.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
