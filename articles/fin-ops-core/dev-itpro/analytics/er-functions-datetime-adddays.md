---
title: ADDDAYS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ADDDAYS elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/03/2019
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
ms.openlocfilehash: 8877bf5a1b6c06e1a25fa9ddaca9c3b039bd2e4d01f39eea9065125977f73e9a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740345"
---
# <a name="adddays-er-function"></a>ADDDAYS ER-funktion

[!include [banner](../includes/banner.md)]

`ADDDAYS`-funktionen beräknar ett *DateTime*-värde som är angivet antal dagar före eller efter ett angivet startdatum.

## <a name="syntax"></a>Syntax

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>Argument

`datetime`: *DateTime*

Ett datum/tidsvärde som representerar startdatumet.

`days`: *Heltal*

Antal dagar före eller efter `datetime`.

## <a name="return-values"></a>Returvärden

*Datum/tid*

Det resulterande datum/tid-värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Ett positivt värde för `days` avkastning ett framtida datum. Ett negativt värde ger ett tidigare datum.

## <a name="example-1"></a>Exempel 1

`ADDDAYS (NOW(), 7)` returnerar datum och tid sju dagar framöver.

## <a name="example-2"></a>Exempel 2

`ADDDAYS (NOW(), -3)` returnerar datum och tid dagar tidigare.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]