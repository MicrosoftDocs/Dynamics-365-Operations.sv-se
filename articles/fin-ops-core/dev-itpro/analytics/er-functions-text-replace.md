---
title: REPLACE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen REPLACE elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 04/02/2020
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
ms.openlocfilehash: 21cdd8532730925b7d5c6f5b3bb565dcd365dd6d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746217"
---
# <a name="replace-er-function"></a>REPLACE ER-funktion

[!include [banner](../includes/banner.md)]

`REPLACE`-funktionen returnerar den angivna textsträngen som ett *sträng* värde när hela eller en del av den har ersatts med en annan sträng.

## <a name="syntax"></a>Syntax

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Den giltiga sökvägen till en datakälla av typen *Sträng*.

`pattern`: *Sträng*

Om `regular expression flag`-argumentet är **FALSKT** innehåller det här argumentet den text som måste ersättas.

Om `regular expression flag`-argumentet är **SANT** innehåller det här argumentet ett reguljärt uttryck som definierar både ett sökmönster och en ersättningstext.

`replacement`: *Sträng*

Om `regular expression flag`-argumentet är **FALSKT** innehåller det här argumentet den text som ersättning.

Om `regular expression flag`-argumentet är **SANT** används inte det här argumentet.

`regular expression flag`: *Boolesk*

Ett *booleskt* värde som anger om ett reguljärt uttryck används för att göra ersättningen.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

Om `regular expression flag`-argumentet är **SANT** returnerar den här funktionen den angivna strängen när den har ändrats genom att använda det reguljära uttrycket som anges av `pattern`-argumentet. Vanliga uttryck används för att hitta tecken som måste ersättas.

Om argumentet `regular expression flag` är **FALSKT**, returnerar funktionen den angivna strängen efter att tecken uppsättningen som har definierats i argumentet `pattern` ersatts av tecknen i argumentet `replacement`. 

## <a name="example-1"></a>Exempel 1

`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` tillämpar ett reguljärt uttryck som tar bort alla icke-numeriska symboler och returnerar **"19234564971"**. 

## <a name="example-2"></a>Exempel 2

`REPLACE ("abcdef", "cd", "GH", false)` ersätter mönstret **"cd"** med strängen **"GH"** och returnerar **"abGHef"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]