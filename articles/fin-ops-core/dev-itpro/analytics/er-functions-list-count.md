---
title: COUNT ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen COUNT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: b3a5bb33964c70c85c7d8571057060c1c2b9d433
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687730"
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
