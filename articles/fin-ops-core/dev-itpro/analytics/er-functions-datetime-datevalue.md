---
title: DATEVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen DATEVALUE elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/04/2019
ms.topic: article
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
ms.openlocfilehash: d760c3f874bfebad11b9497b136cb67df4e9ea61
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746949"
---
# <a name="datevalue-er-function"></a>DATEVALUE ER-funktion

[!include [banner](../includes/banner.md)]

`DATEVALUE`-funktionen returnerar ett värde för *Datum* som konverteras från ett givet textvärde i angivet format och i en valfri angiven [kultur](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) till ett datumvärde. Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Syntax 1

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a>Syntax 2

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Text som representerar värdet till format.

`format`: *Sträng*

Formatet för en given text.

`culture`: *Sträng*

Den kultur som används för att formatera den givna texten.

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