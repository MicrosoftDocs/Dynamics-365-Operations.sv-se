---
title: LISTOFFIRSTITEM ER-funktion
description: Den här artikeln innehåller information om hur funktionen LISTOFFIRSTITEM elektronisk rapportering (ER) används.
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
ms.openlocfilehash: dede32c58ef8dc67028ea17b8a26189f62f73593
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275598"
---
# <a name="listoffirstitem-er-function"></a>LISTOFFIRSTITEM ER-funktion

[!include [banner](../includes/banner.md)]

`LISTOFFIRSTITEM`-funktionen returnerar ett *postlist*-värde som endast består av den första posten i den angivna listan.

## <a name="syntax"></a>Syntax

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="example"></a>Exempel

Uttrycket `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returnerar textvärdet **"A"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
