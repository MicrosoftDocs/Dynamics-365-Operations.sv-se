---
title: WHERE ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen WHERE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: ca218f87eb1f9235ab475809fbbdfecf3fe0c7fb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566052"
---
# <a name="where-er-function"></a>WHERE ER-funktionen

[!include [banner](../includes/banner.md)]

`WHERE`-funktionen returnerar den angivna listan som ett värde för *postlista* efter att den har filtreras enligt det angivna villkoret.

## <a name="syntax"></a>Syntax

```vb
WHERE (list, condition)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

`condition`: *Boolesk*

Ett giltigt villkorsuttryck som används för att filtrera poster i den angivna listan.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Till skillnad från funktionen [FILTER](er-functions-list-filter.md) tillämpas angivet villkor på alla ER-datakällor (elektronisk rapportering) av typen *Postlista* som finns i minnet.

Om argumenten som har konfigurerats för den här funktionen (`list` och `condition`) tillåter att den här begäran översätts till direkt SQL-anrop, genereras ett varningsmeddelande vid designtillfället. Det här meddelandet informerar användaren om att prestanda kan förbättras om [FILTER](er-functions-list-filter.md) funktionen används i stället för `WHERE`.

## <a name="example-1"></a>Exempel 1

Om **Leverantör** konfigureras som en ER-datakälla som refererar till registret VendTable, returnerar uttrycket `WHERE (Vendors, Vendors.VendGroup = "40")` en lista över endast de leverantörer som ingår i leverantörsgrupp 40.

## <a name="example-2"></a>Exempel 2

Om du anger datakällans **DS** för typen *Beräknat fält* och den innehåller uttrycket , kommer uttrycket `SPLIT ("A|B|C", "|")` returnera uttrycket `WHERE( DS, DS.Value = "B")` en lista över en post innehåller text **"B"** i fältet **Värde**.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]