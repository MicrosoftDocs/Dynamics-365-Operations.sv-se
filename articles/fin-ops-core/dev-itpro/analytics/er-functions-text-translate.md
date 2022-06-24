---
title: Funktionen TRANSLATE ER
description: Den här artikeln innehåller information om hur funktionen TRANSLATE elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 04/02/2020
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
ms.openlocfilehash: cf44ad5518e2850d4d4e7fd34866ee2f8313c356
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894336"
---
# <a name="translate-er-function"></a>Funktionen TRANSLATE ER

[!include [banner](../includes/banner.md)]

Funktionen `TRANSLATE` returnerar ett *sträng*-värde som innehåller resultatet av teckenersättningen för angiven text i tecken som ingår i en annan uppsättning.

## <a name="syntax"></a>Syntax

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Den giltiga sökvägen till en datakälla av typen *Sträng*.

`pattern`: *Sträng*

Den text som måste bytas ut.

`replacement`: *Sträng*

Den text som ska användas som ersättning.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

Funktionen `TRANSLATE` ersätter ett tecken i taget. Funktionen ersätter det första tecknet i `text`-argumentet med `pattern`-argumentets första tecken och sedan det andra tecknet och följer samma flöde tills det är klart. När ett tecken från `text` och `pattern`-argumenten matchar ersätts det med ett tecken från `replacement`-argumentet som ligger på samma position som tecknet från `pattern`-argumentet. Om ett tecken förekommer flera gånger i `pattern`-argumentet, används `replacement` argumentmappning som motsvarar den första förekomsten av det här tecknet.

## <a name="example-1"></a>Exempel 1

`TRANSLATE ("abcdef", "cd", "GH")` ersätter tecknet **"c"** i **den angivna "abcdef"**-texten med tecknet **"G"** i `replacement`-texten på grund av följande:
-   Tecknet **"c"** visas i `pattern`-texten i den första positionen.
-   Den första positionen av `replacement`-texten innehåller tecknet **"G"**.

## <a name="example-2"></a>Exempel 2

`TRANSLATE ("abcdef", "ccd", "GH")` returnerar **"abGdef"**.

## <a name="example-3"></a>Exempel 3

`TRANSLATE ("abccba", "abc", "123")` returnerar **"123321"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]