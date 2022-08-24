---
title: ABS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ABS elektronisk rapportering (ER) används.
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
ms.openlocfilehash: a8d0fe68232d9dd27d9ba0cc6b81c7708d22711e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272571"
---
# <a name="abs-er-function"></a>ABS ER-funktion

[!include [banner](../includes/banner.md)]

`ABS`-funktionen returnerar absolutvärdet (modul) för det angivna talet som ett *verkligt* värde. Med andra ord returnera tal utan tecken.

## <a name="syntax"></a>Syntax

```vb
ABS (number)
```

## <a name="arguments"></a>Argument

`number`: *Realtaltal*

Ett numeriskt värde som du vill ha modul för.

## <a name="return-values"></a>Returvärden

*Realtal*

Det resulterande numeriska värdet.

## <a name="example"></a>Exempel

`ABS (-1)` returnerar **1**.

## <a name="additional-resources"></a>Ytterligare resurser

[Matematiska funktioner](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
