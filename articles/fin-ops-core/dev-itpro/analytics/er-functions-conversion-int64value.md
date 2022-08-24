---
title: INT64VALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen INT64VALUE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 4af6cd4ba8b08fe00f53e9dfb1a9156354ec17fc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292599"
---
# <a name="int64value-er-function"></a>INT64VALUE ER-funktion

[!include [banner](../includes/banner.md)]

`INT64VALUE`-funktionen returnerar ett *Int64*-värde som representerar den angivna strängen.

## <a name="syntax-1"></a>Syntax 1

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a>Syntax 2

```vb
INT64VALUE (number)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett textvärde som måste konverteras till ett *Int64*-nummer.

`number`: *Realtal* eller *heltal*

Ett numeriskt värde för *Realtal* eller *Heltal* som måste konverteras till ett *Int64*-nummer.

## <a name="return-values"></a>Returvärden

*Int64*

Det resulterande numeriska värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Eventuella decimaler trunkeras.

## <a name="example-1"></a>Exempel 1

`INT64VALUE ("22565422744")`-returnerar *Int64*-värdet **22565422744**.

## <a name="example-2"></a>Exempel 2

`INT64VALUE ( VALUE("22565422744.77"))`-returnerar *Int64*-värdet **22565422744**.

## <a name="additional-resources"></a>Ytterligare resurser

[Funktioner för typkonvertering](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
