---
title: CONCATENATE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CONCATENATE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 04c7b32e2a9578f8864570a552817ec3ce28fa43
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041200"
---
# <a name="CONCATENATE">CONCATENATE ER-funktion</a>

[!include [banner](../includes/banner.md)]

`CONCATENATE`-funktionen returnerar alla angivna textsträngar som ett *sträng*-värde när de har sammanfogas till en sträng.

## <a name="syntax"></a>Syntax

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argument

`text 1`: *Sträng*

En referens till en datakälla av datatypen *Sträng*. Detta argument krävs.

`text N`: *Sträng*

En referens till en datakälla av datatypen *Sträng*. Dessa ytterligare argument är valfria.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`CONCATENATE ("abc", "def")` returnerar **"abcdef"**.

## <a name="usage-notes"></a>Användningsanteckningar

Uttrycket `"abc" & "def"` returnerar också **"abcdef"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)
