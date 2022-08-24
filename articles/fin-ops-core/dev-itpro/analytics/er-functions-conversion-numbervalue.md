---
title: NUMBERVALUE ER-funktion
description: Den här artikeln innehåller information om hur funktionen NUMBERVALUE elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2e39cf59cabd44583e78ff2c35a7ae4d6edbd7ee
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282604"
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
