---
title: CN_GBT_ADDITIONALDIMENSIONID ER-funktion
description: Den här artikeln innehåller information om hur funktionen CN_GBT_ADDITIONALDIMENSIONID elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/17/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 0ed2593f865a4764b1c6172722d701a0a10ba5f8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281765"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a>CN_GBT_ADDITIONALDIMENSIONID ER-funktion

[!include [banner](../includes/banner.md)]

`CN_GBT_ADDITIONALDIMENSIONID`-funktionen returnerar ett *sträng*-värde som representerar ett enda ekonomisk dimensions-ID som hämtas från den angivna strängen. Den angivna strängen visar alla dimensioner som en kommaseparerad lista med ID:n.

## <a name="syntax"></a>Syntax

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett *sträng*-värde som visar alla dimensioner som en kommaseparerad lista med ID:n.

`number`: Heltal

Värdet *heltal* definierar den begärda dimensionens seriekod i den angivna strängen.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returnerar **"CC"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
