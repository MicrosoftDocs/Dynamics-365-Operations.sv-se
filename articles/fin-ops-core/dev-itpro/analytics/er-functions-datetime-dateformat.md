---
title: Funktionen DATEFORMAT ER
description: Det här avsnittet innehåller information om hur funktionen DATEFORMAT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 01/04/2021
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
ms.openlocfilehash: 1b3a0a2608328b233004034f7ab2ccfa833c17e3
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890920"
---
# <a name="dateformat-er-function"></a>Funktionen DATEFORMAT ER

[!include [banner](../includes/banner.md)]

`DATEFORMAT`-funktionen returnerar ett värde för *Sträng* som visar ett givet datumvärde som text i angivet format och i en valfri angiven [kultur](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes). Om du vill ha mer information om format som stöds, se [Standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) och [Anpassat](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Syntax 1

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a>Syntax 2

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a>Argument

`date`: *Datum*

Ett datumvärde som representerar datumet som ska formateras.

`format`: *Sträng*

Formatet på utdatasträngen

> [!NOTE]
> Formatsträngen är skiftlägeskänslig när du använder antingen ett standardformat eller ett anpassat format. Till exempel [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) "d" formatspecificeraren returnerar datumet med hjälp av det korta datummönstret, medan standard "D" formatspecificeraren returnerar datumet med hjälp av det långa datummönstret. Dessutom returnerar den [anpassade](/dotnet/standard/base-types/custom-date-and-time-format-strings) "M" formatspecificeraren månaden från 1 till 12, medan den anpassade "m" formatspecificeraren returnerar minuten från 0 till 59.

`culture`: *Sträng*

Kulturen som ska användas för formatering.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande strängvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

När kulturen inte definieras som ett argument för den anropade funktionen definieras värdet av `culture` den anropande kontexten. Om till exempel funktionen `DATEFORMAT` anropas med syntax 1 i ett format för elektronisk rapportering (ER) för ett **FIL**-element som är konfigurerat för att använda den tyska kulturen, sker konverteringen med hjälp av den tyska kulturen. Standardvärdet `culture` är **EN-US**.

## <a name="example-1"></a>Exempel 1

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returnerar det aktuella datumet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.

## <a name="example-2"></a>Exempel 2

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returnerar det aktuella datumet för programsessionen, 24 december 2015 som strängen **"2015-12-24"**, baserat på den valda tyska kulturen och det angivna formatet.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]