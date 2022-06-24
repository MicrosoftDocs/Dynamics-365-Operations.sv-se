---
title: FIRSTORNULL ER-funktion
description: Den här artikeln förklarar hur funktionen FIRSTORNULL elektronisk rapportering (ER) används
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
ms.openlocfilehash: bae2916371cd00810f559ff2006b2b238c8ad918
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900263"
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