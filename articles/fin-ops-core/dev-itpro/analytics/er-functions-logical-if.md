---
title: IF ER-funktion
description: Det här avsnittet innehåller information om hur funktionen IF elektronisk rapportering (ER) används.
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
ms.openlocfilehash: b29302ffe534f2439519e57c6a6b8c94c1df8d62
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917153"
---
# <a name="IF">IF ER-funktion</a>

[!include [banner](../includes/banner.md)]

`IF`-funktionen returnerar det första definierade värdet när det definierade villkoret uppfylls. Returnera annars det andra angivna värdet. Värdet som returneras kan vara ett värde för någon av datatyperna som stöds.

## <a name="syntax"></a>Syntax

```
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a>Argument

`condition`: *Boolesk*

Ett giltigt villkorsuttryck som måste testas.

`first value`: *Någon av de datatyper som stöds*

Resultatet som returneras om villkoret uppfylls.

`second value`: *Någon av de datatyper som stöds*

Resultatet som returneras om villkoret inte uppfylls.

## <a name="return-values"></a>Returvärden

*Någon av de datatyper som stöds*

Resultatvärdet för någon av datatyperna som stöds.

## <a name="usage-notes"></a>Användningsanteckningar

`first value` och `second value`-argumenten måste anges med samma datatyp. Ett undantag genereras vid designtillfället om datatyperna för de konfigurerade värdena inte matchar.

Om det första värdet och det andra värdet är värden för datatypen *behållare (post*) eller *postlista*, har resultatet bara de fält som finns i båda värdena.

## <a name="example"></a>Exempel

`IF (1=2, "condition is met", "condition is not met")` returnerar strängen **"villkoret är inte uppfyllt"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Logiska funktioner](er-functions-category-logical.md)
