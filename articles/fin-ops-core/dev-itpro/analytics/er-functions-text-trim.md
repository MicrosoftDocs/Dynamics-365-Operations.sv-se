---
title: TRIM ER-funktion
description: Det här avsnittet innehåller information om hur funktionen TRIM elektronisk rapportering (ER) används.
author: kfend
ms.date: 02/28/2022
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
ms.openlocfilehash: 95b8d2989d705c4998da0af8e683adf567edfe92
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273111"
---
# <a name="trim-er-function"></a>TRIM ER-funktion

[!include [banner](../includes/banner.md)]

`TRIM`-funktionen returnerar den angivna textsträngen som ett *String*-värde efter tabb, carriage return, radflöde och formulärflödestecken har ersatts med ett blanksteg, efter att inledande och avslutande blanksteg har trunkerats samt efter att flera blanksteg mellan ord har tagits bort.

## <a name="syntax"></a>Syntax

```vb
TRIM (text)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Den giltiga sökvägen till en datakälla av typen *Sträng*.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

I vissa fall kanske du vill trunkera inledande och avslutande blanksteg, men föredrar att behålla formateringen för den angivna texten. Om den här texten till exempel representerar en adress som kan anges i textrutan med flera rader och kan innehålla radflöde och formatering av carriage return. I det här fallet ska du använda följande uttryck: `REPLACE(text,"^[ \t]+|[ \t]+$","", true)`, där `text` är det argument som refererar till den angivna textsträngen.

## <a name="example-1"></a>Exempel 1

`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returnerar **"Exempeltext"**.

## <a name="example-2"></a>Exempel 2

`TRIM (CONCATENATE (CHAR(10), "`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(9),"`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(13)))` returnerar **"Exempeltext"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)

[REPLACE ER-funktion](er-functions-text-replace.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
