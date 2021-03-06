---
title: INT64VALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen INT64VALUE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 89a26e867579bcb34a9bae33fa0b98e1ecfe9995
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755406"
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