---
title: Funktionen NUMBERFORMAT ER
description: Det här avsnittet innehåller information om hur funktionen NUMBERFORMAT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 2c3907d1d2c74c852f4f90731e5f4bc23bfbd717
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680276"
---
# <a name="numberformat-er-function"></a>Funktionen NUMBERFORMAT ER

[!include [banner](../includes/banner.md)]

`NUMBERFORMAT`-funktionen returnerar ett värde för *Sträng* som visar det angivna numret i det angivna formatet och i en valfri angiven [kultur](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes). Om du vill ha mer information om format som stöds, se [Standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) och [Anpassat](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).

## <a name="syntax-1"></a>Syntax 1

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a>Syntax 2

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a>Argument

`number`: *Heltal* eller *Realtal*

Ett numeriskt värde som anger det tal som måste formateras.

`format`: *Sträng*

Ett *sträng*-värde som representerar det formatet.

`culture`: *Sträng*

Ett *sträng* värde som representerar kulturen som ska användas för formatering.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

Om kulturen inte definieras som ett argument för den anropade funktionen, avgör kontexten som den här funktionen körs i den kultur som används för att formatera tal.

## <a name="example-1"></a>Exempel 1

För en **EN-US**-kultur returnerar `NUMBERFORMAT (0.45, "p")` **"45,00 %"** och `NUMBERFORMAT (10.45, "#")` returnerar **"10"**.

## <a name="example-2"></a>Exempel 2

`NUMBERFORMAT (10/3, "F2", "de")` returnerar **3,33**, medan `NUMBERFORMAT (10/3, "F2", "en-us")` returnerar **3,33**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)
