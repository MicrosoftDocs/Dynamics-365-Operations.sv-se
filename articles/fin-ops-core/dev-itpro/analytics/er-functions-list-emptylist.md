---
title: Funktionen EMPTYLIST ER
description: Den här artikeln innehåller information om hur funktionen EMPTYLIST elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 5fd14456a615d5dc6fb565f4bed523db5432c871
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268129"
---
# <a name="emptylist-er-function"></a>Funktionen EMPTYLIST ER

[!include [banner](../includes/banner.md)]

`EMPTYLIST`-funktionen returnerar en tomt värde för *Postlista* genom att använda den definierade en lista som källa för liststrukturen.

## <a name="syntax"></a>Syntax

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="example"></a>Exempel

`EMPTYLIST (SPLIT ("abc", 1))` returnerar en ny tom lista som har samma struktur som listan som returneras från `SPLIT`-funktionen som används.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
