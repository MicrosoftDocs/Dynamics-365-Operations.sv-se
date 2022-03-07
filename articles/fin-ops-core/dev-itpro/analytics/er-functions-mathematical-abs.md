---
title: ABS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ABS elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: db12ddddb087556414e81d646c4c87d273a77c133e49152091452d0731916e93
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776084"
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