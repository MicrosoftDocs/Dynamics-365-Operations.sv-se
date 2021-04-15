---
title: CN_GBT_ADDITIONALDIMENSIONID ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CN_GBT_ADDITIONALDIMENSIONID elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/17/2019
ms.topic: article
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
ms.openlocfilehash: ac0b54476265171b3826e43600f99097701231e1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744401"
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