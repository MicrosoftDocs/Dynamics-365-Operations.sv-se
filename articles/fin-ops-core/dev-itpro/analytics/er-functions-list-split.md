---
title: Funktionen SPLIT ER
description: Det här avsnittet innehåller information om hur funktionen SPLIT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 806a0995f0c138f4e80396bb993bc6f41bc7c827
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567352"
---
# <a name="split-er-function"></a>Funktionen SPLIT ER

[!include [banner](../includes/banner.md)]

`SPLIT`-funktionen delar den angivna indatasträngen i delsträngar och returnerar resultatet som ett nytt värde för *postlistan*.

## <a name="syntax-1"></a>Syntax 1

```vb
SPLIT (input, length)
```

Denna syntax används för att dela upp den definierade indatasträngen i delsträngar som var och en är av den definierade längden.

## <a name="syntax-2"></a>Syntax 2

```vb
SPLIT (input, delimiter)
```

Dennna syntax används för att dela upp den definierade indatasträngen i delsträngar baserat på den definierade avgränsaren.

## <a name="arguments"></a>Argument

`input`: *Sträng*

Texten som ska delas upp

`length`: *Heltal*

Den maximala längden för en enskild delsträng.

`delimiter`: *Sträng*

En avgränsare som används för att avgränsa delsträngar.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Poststrukturen i listan som returneras består av fältet **Värde** av typen *Sträng*. Varje post i listan som returneras innehåller genererade delsträngar i det här fältet.

Om argumentet `delimiter` är tom returneras en ny lista som består av en post med ett fält för **Värde** av typen *Sträng*. Det här fältet innehåller indatatext.

Om argumentet `input` är tomt returneras en tom ny lista. Om antingen `input` eller `delimiter` är ospecificerad (null) kastas ett programundantag.

## <a name="example-1"></a>Exempel 1

`SPLIT ("abcd", 3)` returnerar en ny lista som består av två poster som har fältet **Värde** av typen *Sträng*. Fältet **Värde** i den första posten innehåller texten **"abc"** och fältet **Värde** i den andra posten innehåller texten **"d**".

## <a name="example-2"></a>Exempel 2

`SPLIT ("XAb aBy", "aB")` returnerar en ny lista som består av tre poster som har fältet **Värde** av typen *Sträng*. Fältet **Värde** i den första posten innehåller texten **"X"**, fältet **Värde** i den andra posten innehåller texten **"&nbsp;"** och fältet **Värde** i den tredje posten innehåller texten **"y"**. 

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]