---
title: ADDDAYS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ADDDAYS elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/03/2019
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
ms.openlocfilehash: 0c420daa04b8e22504d25d317c75826f1d1914b7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747069"
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