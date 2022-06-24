---
title: CASE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CASE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: f8ce598315bfbf291fafc6c9c9d54133486fb352
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854768"
---
# <a name="case-er-function"></a>CASE ER-funktion

[!include [banner](../includes/banner.md)]

`CASE`-funktionen utvärderar värdet för det angivna uttrycket mot de angivna alternativa och returnerar resultatet av det första alternativet som är lika med värdet för det angivna uttrycket. Annars returneras ett valfritt standard resultat om ett standard resultat anges som det sista argumentet för den anropade funktionen som inte föregås av ett alternativ. Värdet som returneras kan vara ett värde för någon av datatyperna som stöds.

## <a name="syntax"></a>Syntax

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a>Argument

`expression`: *Primitiv datatyp* (booleskt, numeriskt eller text)

Ett giltigt uttryck som returnerar ett värde av den primitiva datatypen.

`option 1`: *Primitiv datatyp* (booleskt, numeriskt eller text)

Ett giltigt uttryck som returnerar ett värde av samma primitiva datatyp som `expression`-argumentet för den anropade funktionen. Detta argument krävs.

`result 1`: *Någon av de datatyper som stöds*

Det returnerade resultatet som motsvarar det föregående alternativet. Detta argument krävs.

`option N`: *Primitiv datatyp* (booleskt, numeriskt eller text)

Ett giltigt uttryck som returnerar ett värde av samma primitiva datatyp som `expression`-argumentet för den anropade funktionen. Detta argument är valfritt.

`result N`: *Någon av de datatyper som stöds*

Det returnerade resultatet som motsvarar det föregående alternativet. Detta argument är valfritt.

`default result`: *Någon av de datatyper som stöds*

Resultatet som ska returneras om det inte finns någon matchning. Detta argument är valfritt.

## <a name="return-values"></a>Returvärden

*Någon av de datatyper som stöds*

Resultatvärdet för någon av datatyperna som stöds.

## <a name="usage-notes"></a>Användningsanteckningar

Ett undantagsfel utlöses vid körning om det inte finns någon matchning och ett valfritt standard resultat inte har definierats.

Alla resultat måste anges med samma datatyp. Ett undantag genereras vid designtillfället om datatyperna för de konfigurerade resultaten inte matchar.

Om det första resultatvärdet och *N* th resultatvärdet är värden för datatypen *behållare (post)* eller *postlista* har resultatet bara de fält som finns i båda värdena.

## <a name="example"></a>Exempel

`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` returnerar strängen **"WINTER"** om det aktuella programsessionsdatumet är mellan oktober och december. Annars returneras en tom sträng.

## <a name="additional-resources"></a>Ytterligare resurser

[Logiska funktioner](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]