---
title: NUMBERVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NUMBERVALUE elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: bcb76310a53c86b68f18085e203d11f405b16946a25fe1be67e649f83335d1f8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733807"
---
# <a name="numbervalue-er-function"></a>NUMBERVALUE ER-funktion

[!include [banner](../includes/banner.md)]

`NUMBERVALUE`-funktionen returnerar ett *verkligt* värde som konverteras från den angivna värdet *strängen*. Under konverteringen beaktas de angivna decimal- och siffergrupperingsavgränsarna.

## <a name="syntax"></a>Syntax

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett textvärde som måste konverteras till ett *Realtal*-nummer.

`decimal separator`: Sträng

En decimalavgränsare. Det används för att separera heltal och fraktionerad delar av ett decimaltal.

`digit grouping separator`: *Sträng*

En siffergrupperingsavgränsare. Den används som tusentalsavgränsare.

## <a name="return-values"></a>Returvärden

*Realtal*

Det resulterande numeriska värdet.

## <a name="example"></a>Exempel

`NUMBERVALUE( "1 234,56", ",", " ")` returnerar **1234.56**.

## <a name="additional-resources"></a>Ytterligare resurser

[Funktioner för typkonvertering](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]