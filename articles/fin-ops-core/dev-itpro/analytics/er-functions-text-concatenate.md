---
title: CONCATENATE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CONCATENATE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
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
ms.openlocfilehash: 6e4800ce44d9da07818acec55c50224a9a000fe6
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569615"
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