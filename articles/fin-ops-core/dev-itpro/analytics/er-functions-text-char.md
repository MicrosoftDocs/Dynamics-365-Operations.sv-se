---
title: CHAR ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CHAR elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: a9f0f70c250592bf74b1a1df823e66803e853a64
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683001"
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

Den sträng som returneras beror på viken kodning som har valts i det överordnade formatelementet **FILE**. För listan över vilka koder som stöds se [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).

## <a name="example"></a>Exempel

`CHAR (255)` returnerar **"ÿ"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)
