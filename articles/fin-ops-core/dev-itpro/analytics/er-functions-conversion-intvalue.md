---
title: INTVALUE ER-funktion
description: Den här artikeln innehåller information om hur funktionen INTVALUE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: eccee60c40bfc96f1fd93e7177207a1dd1888dc6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282634"
---
# <a name="intvalue-er-function"></a>INTVALUE ER-funktion

[!include [banner](../includes/banner.md)]

`INTVALUE`-funktionen returnerar ett *Int*-värde som representerar den angivna strängen.

## <a name="syntax-1"></a>Syntax 1

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a>Syntax 2

```vb
INTVALUE (number)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett textvärde som måste konverteras till ett *Int*-nummer.

`number`: *Realtal* eller *heltal*

Ett numeriskt värde för *Realtal* eller *Heltal* som måste konverteras till ett *Int*-nummer.

## <a name="return-values"></a>Returvärden

*Int*

Det resulterande numeriska värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Eventuella decimaler trunkeras.

## <a name="example-1"></a>Exempel 1

`INTVALUE ("100.77")`-returnerar *Int*-värdet **100**.

## <a name="example-2"></a>Exempel 2

`INTVALUE (-100.77)`-returnerar *Int*-värdet **-100**.

## <a name="additional-resources"></a>Ytterligare resurser

[Funktioner för typkonvertering](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
