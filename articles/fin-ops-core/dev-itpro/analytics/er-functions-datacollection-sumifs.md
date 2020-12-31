---
title: SUMIFS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen SUMIFS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: d9d9ef51f3c8cb090f940670c4c3afae104268ed
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687972"
---
# <a name="sumifs-er-function"></a>SUMIFS ER-funktion

[!include [banner](../includes/banner.md)]

`SUMIFS`-funktionen returnerar ett värde för *Realtal* som representerar summan av värden som returneras av bindningar av formatelement och samlas in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret. Varje villkor består av ett nyckelintervall och ett nyckelvärde.

## <a name="syntax"></a>Syntax

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>Argument

`key name for summing`: *Sträng*

Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för formatkomponenten elektronisk rapportering (ER) som värdet för bindningen måste användas för summeringsändamål.

Egenskapen **Collected data key name** kan konfigureras för antingen en **Numerisk**-komponent eller en **Sträng**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.

`condition 1 range`: *Sträng*

Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för en komponent för ER-format. Det här argumentet är obligatoriskt.

Egenskapen **Collected data key name** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.

`condition 1 value`: *Sträng*

Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key value** för en komponent för ER-format. Det här argumentet är obligatoriskt.

Egenskapen **Collected data key value** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.

`condition N range`: *Sträng*

Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för en komponent för ER-format. Dessa ytterligare argument är valfria.

Egenskapen **Collected data key name** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.

`condition N value`: *Sträng*

Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key value** för en komponent för ER-format. Dessa ytterligare argument är valfria.

Egenskapen **Collected data key value** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponent i ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output detail** är aktiverat.

## <a name="return-values"></a>Returvärden

*Realtal*

Det resulterande numeriska värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Denna funktion returnerar ett **0** (noll) värde när alternativet **Collect output details** för den aktuella komponenten **gemensam\\fil** är inaktiverad.

I `condition range`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.

I `condition value`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.

## <a name="example"></a>Exempel

För mer information om att använda den här funktionen, se uppgiftsguiden [ER Använd data från formatutmatningen för inventering och summering](tasks/er-format-counting-summing-1.md) (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner.

## <a name="additional-resources"></a>Ytterligare resurser

[Datainsamlingsfunktioner](er-functions-category-data-collection.md)
