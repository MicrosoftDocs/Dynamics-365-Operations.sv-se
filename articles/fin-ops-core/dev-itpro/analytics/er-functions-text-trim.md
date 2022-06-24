---
title: TRIM ER-funktion
description: Det här avsnittet innehåller information om hur funktionen TRIM elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 02/28/2022
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
ms.openlocfilehash: deadf89641771efa864e701af9dad57c5e62ea37
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864671"
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
