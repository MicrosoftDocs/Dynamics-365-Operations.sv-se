---
title: ISVALIDCHARACTERISO7064 ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ISVALIDCHARACTERISO7064 elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 26ee54d1c3cd5673ec573e2df688780d3902b69d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275388"
---
# <a name="isvalidcharacteriso7064-er-function"></a>ISVALIDCHARACTERISO7064 ER-funktion

[!include [banner](../includes/banner.md)]

`ISVALIDCHARACTERISO7064`-funktionen returnerar ett *booleskt* värde för **SANT** när en specificerad sträng representerar ett giltigt internationellt bankkontonummer (IBAN). Annars returnerar uttrycket värdet *boolesk* av **FALSK**.

## <a name="syntax"></a>Syntax

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett textvärde som representerar ett IBAN.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returnerar **"SANT**. 

`ISVALIDCHARACTERISO7064 ("AT61")` returnerar **FALSKT**.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
