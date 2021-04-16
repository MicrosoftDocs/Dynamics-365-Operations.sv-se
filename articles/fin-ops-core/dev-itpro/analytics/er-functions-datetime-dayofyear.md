---
title: DAYOFYEAR ER-funktion
description: Det här avsnittet innehåller information om hur funktionen DAYOFYEAR elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 569e988db91ff992fb7db6e7fd6e8c6aa6a1a3e8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746925"
---
# <a name="dayofyear-er-function"></a>DAYOFYEAR ER-funktion

[!include [banner](../includes/banner.md)]

Funktionen `DAYOFYEAR` returnerar värdet *heltal* som representerar antalet dagar mellan 1 januari och det angivna datumet.

## <a name="syntax"></a>Syntax

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a>Argument

`date`: *Datum*

Ett datumvärde som representerar det datum som ska användas för beräkningen av antalet dagar.

## <a name="return-values"></a>Returvärden

*Heltal*

Det resulterande numeriska värdet.

## <a name="example-1"></a>Exempel 1

`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returnerar **61**.

## <a name="example-2"></a>Exempel 2

`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returnerar **1**.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]