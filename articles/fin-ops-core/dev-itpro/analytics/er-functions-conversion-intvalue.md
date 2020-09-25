---
title: INTVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen INTVALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5c3e4c8bd918fa1154d2c111970d2f6d0e90e08
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743649"
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
