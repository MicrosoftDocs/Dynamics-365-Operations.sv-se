---
title: FIRSTORNULL ER-funktion
description: Det här avsnittet förklarar hur funktionen FIRSTORNULL elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: 18c8f79d7d6306d9973c5a3f129b9cde38d05d58502a2c83ac89a2bd10aaaeab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749719"
---
# <a name="firstornull-er-function"></a>FIRSTORNULL ER-funktion

[!include [banner](../includes/banner.md)]

`FIRSTORNULL`-funktionen returnerar den första posten i den angivna listan som ett *behållarvärde (post)* om posten inte är tom. Om posten är tom returnerar den här funktionen ett nullvärde *behållare (post)*.

## <a name="syntax"></a>Syntax

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

## <a name="return-values"></a>Returvärden

*Behållare (post)*

Det resulterande postvärdet.

## <a name="example"></a>Exempel

Uttrycket `FIRSTORNULL(SPLIT("",1)).Value` returnerar en tom sträng (**""**).

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]