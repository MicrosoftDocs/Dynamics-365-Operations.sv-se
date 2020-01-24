---
title: ADDDAYS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ADDDAYS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd1290538c506cd0db6eb21a304ff9812c808f17
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916463"
---
# <a name="ADDDAYS">ADDDAYS ER-funktion</a>

[!include [banner](../includes/banner.md)]

`ADDDAYS`-funktionen beräknar ett *DateTime*-värde som är angivet antal dagar före eller efter ett angivet startdatum.

## <a name="syntax"></a>Syntax

```
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
