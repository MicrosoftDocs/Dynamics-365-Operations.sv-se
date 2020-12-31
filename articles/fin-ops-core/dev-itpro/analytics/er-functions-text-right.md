---
title: RIGHT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen RIGHT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 13884182cb986564e81f310993747997341ffc07
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682953"
---
# <a name="right-er-function"></a>RIGHT ER-funktion

[!include [banner](../includes/banner.md)]

`RIGHT`-funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från slutet av den angivna strängen.

## <a name="syntax"></a>Syntax

```vb
RIGHT (text, number)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett *sträng*-värde som representerar den ursprungliga texten.

`number`: *Heltal*

Antalet tecken som måste returneras från slutet av den ursprungliga texten.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`RIGHT ("Sample", 3)` returnerar **"ple"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)
