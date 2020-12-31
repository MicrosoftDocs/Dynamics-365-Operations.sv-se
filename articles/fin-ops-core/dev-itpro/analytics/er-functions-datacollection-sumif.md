---
title: SUMIF ER-funktion
description: Det här avsnittet innehåller information om hur funktionen SUMIF elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 04/27/2020
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
ms.openlocfilehash: 52f9cdb78efa6fe0dbebd2ffd78cd6e9185d6b2e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685361"
---
# <a name="sumif-er-function"></a>SUMIF ER-funktion

[!include [banner](../includes/banner.md)]

`SUMIF`-funktionen returnerar ett värde för *Realtal* som representerar summan av värden som returneras av bindningar av formatelement och samlas in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret. Villkoret består av ett nyckelintervall och ett nyckelvärde.

## <a name="syntax"></a>Syntax

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a>Argument

`key name for summing`: *Sträng*

Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för formatkomponenten elektronisk rapportering (ER) som värdet för bindningen måste användas för summeringsändamål.

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

Mer information och exempel på hur du använder funktionen finns i [Skjuta upp körning av serieelement i ER-format](er-defer-sequence-element.md#Example) och [Senarelägg körning av XML-element i ER-format](er-defer-xml-element.md#Example).

## <a name="additional-resources"></a>Ytterligare resurser

[Datainsamlingsfunktioner](er-functions-category-data-collection.md)
