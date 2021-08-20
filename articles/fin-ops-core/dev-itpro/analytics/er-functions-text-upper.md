---
title: UPPER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen UPPER elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 3742f490fb87d156e3b3dcebabdcebb85ab76f5d0afd9a60806497d32e5746e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6729816"
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