---
title: INTVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen INTVALUE elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 71eedde5a22f36a8a827824087633de32c00cc7d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755382"
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