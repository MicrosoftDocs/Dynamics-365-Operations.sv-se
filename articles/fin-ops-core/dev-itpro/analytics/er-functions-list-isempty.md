---
title: Funktionen ISEMPTY ER
description: Det här avsnittet innehåller information om hur funktionen ISEMPTY elektronisk rapportering (ER) används.
author: NickSelin
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
ms.openlocfilehash: 9c33e8b613bf5bf5bc17a42a7668d4cc4ee58e53
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750446"
---
# <a name="isempty-er-function"></a>Funktionen ISEMPTY ER

[!include [banner](../includes/banner.md)]

`ISEMPTY`-funktionen returnerar *booleskt* värde för **SANT** om den angivna listan inte innehåller några poster. Annars returnerar uttrycket värdet *boolesk* av **FALSK**.

## <a name="syntax"></a>Syntax

```vb
ISEMPTY (list)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

## <a name="return-values"></a>Returvärden

*Boolesk*

Det resulterande *booleska* värdet.

## <a name="example-1"></a>Exempel 1

Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `ISEMPTY(DS)` att returnera **FALSK**.

## <a name="example-2"></a>Exempel 2

Uttrycket `ISEMPTY (SPLIT ("",1))` returnerar **SANT**.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]