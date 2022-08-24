---
title: CONCATENATE ER-funktion
description: Den här artikeln innehåller information om hur funktionen CONCATENATE elektronisk rapportering (ER) används
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
ms.openlocfilehash: 230bbbac5df7824c3ef7d0550cc45dbf6c374858
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267297"
---
# <a name="concatenate-er-function"></a>CONCATENATE ER-funktion

[!include [banner](../includes/banner.md)]

`CONCATENATE`-funktionen returnerar alla angivna textsträngar som ett *sträng*-värde när de har sammanfogas till en sträng.

## <a name="syntax"></a>Syntax

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argument

`text 1`: *Sträng*

En referens till en datakälla av datatypen *Sträng*. Detta argument krävs.

`text N`: *Sträng*

En referens till en datakälla av datatypen *Sträng*. Dessa ytterligare argument är valfria.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`CONCATENATE ("abc", "def")` returnerar **"abcdef"**.

## <a name="usage-notes"></a>Användningsanteckningar

Uttrycket `"abc" & "def"` returnerar också **"abcdef"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
