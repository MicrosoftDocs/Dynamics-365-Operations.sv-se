---
title: Funktionen EMPTYLIST ER
description: Det här avsnittet innehåller information om hur funktionen EMPTYLIST elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: f6c2777065656affc992a427194286008c1df42f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559210"
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