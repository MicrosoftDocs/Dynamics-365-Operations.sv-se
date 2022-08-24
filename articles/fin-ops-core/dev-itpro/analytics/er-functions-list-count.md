---
title: COUNT ER-funktionen
description: Den här artikeln innehåller information om hur funktionen COUNT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 64c8be659b564d612f3127d46e54535c73ae21ce
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287261"
---
# <a name="count-er-function"></a>COUNT ER-funktionen

[!include [banner](../includes/banner.md)]

`COUNT`-funktionen returnerar ett *heltalsvärde* som representerar antalet poster i den angivna listan, om listan inte är tom. Om listan är tom returnerar den här funktionen **0** (noll).

## <a name="syntax"></a>Syntax

```vb
COUNT (list)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

## <a name="return-values"></a>Returvärden

*Heltal*

Det resulterande numeriska värdet.

## <a name="example"></a>Exempel

`COUNT (SPLIT("abcd" , 3))` returnerar **2** eftersom `SPLIT`-funktionen som används i det här exemplet skapar en lista som består av två poster.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
