---
title: AND ER-funktion
description: Det här avsnittet innehåller information om hur funktionen AND elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: bd31fc008b066d7e7d68588c41296537975c2b5c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894365"
---
# <a name="and-er-function"></a>AND ER-funktion

[!include [banner](../includes/banner.md)]

`AND`-funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant. Annars returnerar uttrycket värdet *boolesk* av **FALSK**.

## <a name="syntax"></a>Syntax

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argument

`condition 1`: *Boolesk*

Ett giltigt villkorsuttryck som måste testas. Detta argument krävs.

`condition N`: *Boolesk*

Ett giltigt villkorsuttryck som måste testas. Dessa ytterligare argument är valfria.

## <a name="return-values"></a>Returvärden

*Boolesk*

Det resulterande *booleska* värdet.

## <a name="usage-notes"></a>Användningsanteckningar

I argumenten för logiska funktioner kan du använda datakällans referenser, numeriska värden och text, booleska värden, jämförelseoperatorer och andra funktioner för elektronisk rapportering (ER). Alla argument måste dock utvärderas till ett *booleskt* värde **SANT** eller **FALSKT**.

## <a name="example"></a>Exempel

`AND (1=1, "a"="a")` returnerar **"SANT**.

`AND (1=2, "a"="a")` returnerar **FALSKT**.

## <a name="additional-resources"></a>Ytterligare resurser

[Logiska funktioner](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]