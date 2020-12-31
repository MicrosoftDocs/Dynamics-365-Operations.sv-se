---
title: NOT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NOT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 2308ab4d222863312441b3f17559ac4d3afbfb29
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686964"
---
# <a name="not-er-function"></a>NOT ER-funktion

[!include [banner](../includes/banner.md)]

`NOT`-funktionen returnerar omvända logiska värdet för det angivna villkoret som ett *Booleskt* värde.

## <a name="syntax"></a>Syntax

```vb
NOT (condition)
```

## <a name="arguments"></a>Argument

`condition`: *Boolesk*

Ett giltigt villkorsuttryck som måste återförd.

## <a name="return-values"></a>Returvärden

*Boolesk*

Det resulterande *booleska* värdet.

## <a name="example"></a>Exempel

`NOT (TRUE)` returnerar **FALSKT**.

## <a name="additional-resources"></a>Ytterligare resurser

[Logiska funktioner](er-functions-category-logical.md)
