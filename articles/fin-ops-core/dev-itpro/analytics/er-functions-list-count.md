---
title: COUNT ER-funktionen
description: Den här artikeln innehåller information om hur funktionen COUNT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: b848bd179806b676435c219f0eb983516f3d0bf9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895407"
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