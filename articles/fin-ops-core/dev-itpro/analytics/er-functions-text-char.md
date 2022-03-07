---
title: CHAR ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CHAR elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: e422ccc406e919b2191f4bccb1ac8198bba84b09e9f01f6971876e2c6507d6d3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754376"
---
# <a name="char-er-function"></a>CHAR ER-funktion

[!include [banner](../includes/banner.md)]

`CHAR`-funktionen returnerar ett *sträng*-värde som visar ett enstaka tecken som refereras av det angivna Unicode-numret.

## <a name="syntax"></a>Syntax

```vb
CHAR (number)
```

## <a name="arguments"></a>Argument

`number`: *Heltal*

Ett tal som motsvarar ett förväntat enstaka tecken.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

Den sträng som returneras beror på viken kodning som har valts i det överordnade formatelementet **FILE**. För listan över vilka koder som stöds se [Encoding class](/dotnet/api/system.text.encoding).

## <a name="example"></a>Exempel

`CHAR (255)` returnerar **"ÿ"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]