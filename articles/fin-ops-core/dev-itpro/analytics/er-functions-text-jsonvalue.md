---
title: JSONVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen JSONVALUE elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/11/2019
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
ms.openlocfilehash: b034755602a2f999892d2b976c80550b7a3d7f3cd179816dd7aa1edefe6a0270
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733783"
---
# <a name="jsonvalue-er-function"></a>JSONVALUE ER-funktion

[!include [banner](../includes/banner.md)]

`JSONVALUE`-funktionen analyserar data i JSON-format (JavaScript Object Notation) som används av den angivna sökvägen och som extraherar ett skalärvärde som baseras på angivet-ID. Den returnerar sedan det extraherade skalärvärdet som ett *sträng* värde.

## <a name="syntax"></a>Syntax

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argument

`input`: *Sträng*

Den giltiga sökvägen till en datakälla av typen *Sträng* som innehåller JSON-data.

`path`: *Sträng*

Identifierare för ett skalärvärde av JSON-data.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

**JsonField** datakälla innehåller följande data JSON-format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**. I det här fallet returnerar uttrycket `JSONVALUE (JsonField, "BuildNumber")` följande värde av datatypen *Sträng*: **"7.3.1234.1"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]