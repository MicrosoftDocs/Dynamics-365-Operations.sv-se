---
title: ADDDAYS ER-funktion
description: Den här artikeln innehåller information om hur funktionen ADDDAYS elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 69273794def0dc52dc8e31615c319ccf5067fa77
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274152"
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
