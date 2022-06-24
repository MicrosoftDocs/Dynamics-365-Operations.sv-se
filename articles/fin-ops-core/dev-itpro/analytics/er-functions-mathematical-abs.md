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
ms.openlocfilehash: 90fbff223be5c195feb66b9ea72ee0688e60697b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886890"
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