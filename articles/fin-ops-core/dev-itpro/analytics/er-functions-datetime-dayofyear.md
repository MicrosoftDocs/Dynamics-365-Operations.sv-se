---
title: DAYOFYEAR ER-funktion
description: Den här artikeln innehåller information om hur funktionen DAYOFYEAR elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: e49a80b2ef3c7defcfc23e868374cec5832dc913
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292569"
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
