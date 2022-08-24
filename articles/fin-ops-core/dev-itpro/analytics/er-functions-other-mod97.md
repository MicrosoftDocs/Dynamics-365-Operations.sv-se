---
title: MOD_97 ER-funktion
description: Den här artikeln innehåller information om hur funktionen MOD_97 elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 55d2bce660186f10fc48e29f5cf03385a778a57a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285228"
---
# <a name="mod_97-er-function"></a>MOD_97 ER-funktion

[!include [banner](../includes/banner.md)]

`MOD_97`-funktionen returnerar ett *sträng*-värde som representerar en betalningsmottagarreferens som ett MOD97-uttryck, baserat på siffrorna i det angivna fakturanumret.

## <a name="syntax"></a>Syntax

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a>Argument

`invoice number digits`: *Sträng*

Ett textvärde som representerar siffrorna i ett fakturanummer.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`MOD_97 ("VEND-200002")` returnerar **"20000285"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
