---
title: Funktionen TRANSLATE ER
description: Det här avsnittet innehåller information om hur funktionen TRANSLATE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 415444bda097c00522155d1b37988a79da836902
ms.sourcegitcommit: fb8ad8e2b142441a6530b364f3258bbcc0c724d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201122"
---
# <a name=""></a><a name="TRANSLATE">Funktionen TRANSLATE ER</a>

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
