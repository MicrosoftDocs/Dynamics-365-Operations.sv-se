---
title: NOT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NOT elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 032cdaa2c71f6fab8c15780594d5a26d73600e74
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278989"
---
# <a name="not-er-function"></a>NOT ER-funktion

[!include [banner](../includes/banner.md)]

`NOT`-funktionen returnerar omvända logiska värdet för det angivna villkoret som ett *Booleskt* värde.

## <a name="syntax"></a>Syntax

```vb
NOT (condition)
```

## <a name="arguments"></a>Argument

`condition`: *Boolesk*

Ett giltigt villkorsuttryck som måste återförd.

## <a name="return-values"></a>Returvärden

*Boolesk*

Det resulterande *booleska* värdet.

## <a name="example"></a>Exempel

`NOT (TRUE)` returnerar **FALSKT**.

## <a name="additional-resources"></a>Ytterligare resurser

[Logiska funktioner](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
