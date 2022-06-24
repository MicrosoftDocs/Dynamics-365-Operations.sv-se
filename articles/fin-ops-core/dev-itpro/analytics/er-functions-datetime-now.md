---
title: NOW ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NOW elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 6b33ac5b46721be16d708df1bfec4b62ef235388
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908544"
---
# <a name="now-er-function"></a>NOW ER-funktion

[!include [banner](../includes/banner.md)]

`NOW`-funktionen returnerar ett *DateTime*-värde som representerar aktuella programmets serverdatum och -tid.

## <a name="syntax"></a>Syntax

```vb
NOW ()
```

## <a name="return-values"></a>Returvärden

*Datum/tid*

Det resulterande datum/tid-värdet.

## <a name="example"></a>Exempel

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returnerar det aktuella datum/tidsvärdet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]