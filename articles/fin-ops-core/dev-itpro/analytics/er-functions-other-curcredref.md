---
title: Funktionen CURCREDREF ER
description: Den här artikeln innehåller information om hur funktionen CURCREDREF elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 543b79a336823f8cbedf80454f5bebecfeca1cc4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274838"
---
# <a name="curcredref-er-function"></a>Funktionen CURCREDREF ER

[!include [banner](../includes/banner.md)]

`CURCREDREF`-funktionen returnerar ett *sträng*-värde som representerar en betalningsmottagarreferens baserat på siffrorna i det angivna fakturanumret.

## <a name="syntax"></a>Syntax

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a>Argument

`invoice number digits`: *Sträng*

Ett textvärde som representerar siffrorna i ett fakturanummer.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`CURCredRef ("VEND-200002")` returnerar **"2200002"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
