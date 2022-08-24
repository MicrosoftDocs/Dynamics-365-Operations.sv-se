---
title: UPPER ER-funktion
description: Den här artikeln innehåller information om hur funktionen UPPER elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: bdea427dda5f09a3903378012679e9dd3fa86be9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275354"
---
# <a name="upper-er-function"></a>UPPER ER-funktion

[!include [banner](../includes/banner.md)]

`UPPER`-funktionen returnerar den angivna textsträngen som ett *sträng* värde efter att den har konverterats till versaler.

## <a name="syntax"></a>Syntax

```vb
UPPER (text )
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Den giltiga sökvägen till en datakälla av typen *Sträng*.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`UPPER ("Sample")` returnerar **"EXEMPEL"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
