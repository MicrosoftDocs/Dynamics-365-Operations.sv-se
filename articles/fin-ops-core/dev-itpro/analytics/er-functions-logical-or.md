---
title: OR ER-funktion
description: Det här avsnittet innehåller information om hur funktionen OR elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: f6751c70599b5e3c05b9d1c69a95e82673b230210170cfead1e6a87c57d59c7f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747579"
---
# <a name="or-er-function"></a>OR ER-funktion

[!include [banner](../includes/banner.md)]

`OR`-funktionen returnerar ett *booleskt* värde på **FALSK** om alla angivna villkor är falsk. Den här funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant.

## <a name="syntax"></a>Syntax

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argument

`condition 1`: *Boolesk*

Ett giltigt villkorsuttryck som måste testas. Detta argument krävs.

`condition N`: *Boolesk*

Ett giltigt villkorsuttryck som måste testas. Dessa ytterligare argument är valfria.

## <a name="return-values"></a>Returvärden

*Boolesk*

Det resulterande *booleska* värdet.

## <a name="example"></a>Exempel

`OR (1=2, "a"="a")` returnerar **"SANT**.

## <a name="additional-resources"></a>Ytterligare resurser

[Logiska funktioner](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]