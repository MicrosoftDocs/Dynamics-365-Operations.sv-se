---
title: IF ER-funktion
description: Den här artikeln innehåller information om hur funktionen IF elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 066cffaebc415305a2481e3bf0f0a5f4e108fabc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844570"
---
# <a name="if-er-function"></a>IF ER-funktion

[!include [banner](../includes/banner.md)]

`IF`-funktionen returnerar det första definierade värdet när det definierade villkoret uppfylls. Returnera annars det andra angivna värdet. Värdet som returneras kan vara ett värde för någon av datatyperna som stöds.

## <a name="syntax"></a>Syntax

```vb
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]