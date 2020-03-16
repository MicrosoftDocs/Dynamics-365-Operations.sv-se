---
title: OR ER-funktion
description: Det här avsnittet innehåller information om hur funktionen OR elektronisk rapportering (ER) används.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a850b1cbe7224ab1a7b2bd39ac4667304781cbb
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041686"
---
# <a name="OR">OR ER-funktion</a>

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
