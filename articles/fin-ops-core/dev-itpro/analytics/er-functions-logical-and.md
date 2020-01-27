---
title: AND ER-funktion
description: Det här avsnittet innehåller information om hur funktionen AND elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: dd9c0ed0238009f70ad7a9bf5a5e19ebfb95cccc
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917176"
---
# <a name="AND">AND ER-funktion</a>

[!include [banner](../includes/banner.md)]

`AND`-funktionen returnerar ett *booleskt* värde på **SANT** om alla angivna villkor är sant. Annars returnerar uttrycket värdet *boolesk* av **FALSK**.

## <a name="syntax"></a>Syntax

```
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
