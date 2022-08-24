---
title: Funktionen NUMERALSTOTEXT ER
description: Den här artikeln innehåller information om hur funktionen NUMERALSTOTEXT elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 172693583699edfad7deeb16f8fc081abb6119d5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288001"
---
# <a name="numeralstotext-er-function"></a>Funktionen NUMERALSTOTEXT ER

[!include [banner](../includes/banner.md)]

`NUMERALSTOTEXT`-funktionen returnerar det angivna talet som ett *sträng*-värde när det har stavats ut (konverteras till textsträngar) på det angivna språket.

## <a name="syntax"></a>Syntax

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a>Argument

`number`: *Heltal* eller *Realtal*

Ett numeriskt värde som anger det tal som måste anges.

`language`: *Sträng*

Ett *sträng*-värde som representerar språkkoden.

`currency`: *Sträng*

Ett *sträng*-värde som representerar valutakoden.

`print currency name flag`: *Boolesk*

Ett *booleskt* värde som anger om ett valutanamn måste läggas till i den stavade texten.

`decimal points`: *Heltal*

Ett *heltals*-värde som anger antalet decimaler som den stavade texten ska ha.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

Språkkod är valfritt. Om den är definierad som en tom sträng används istället språkkoden för löpande kontext. Standardspråk är **EN-US**. Språkkoden för den löpande kontexten definieras i en **mapp** eller **fil**-element i det elektroniska rapporteringsformatet (ER) som körs.

Valutakoden är valfri. Om den är definierad som en tom sträng används istället företagsvaluta för löpande kontext.

> [!NOTE] 
> Argumenten `print currency name flag` och `decimal points` analyseras endast för följande språkkoder: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** och **RU**. I tillägg analyseras argumentet `print currency name flag` endast för företag vars länder eller regioner stöder valutanamnnedgång.

## <a name="example-1"></a>Exempel 1

`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returnerar **"1234 och 56"**.

## <a name="example-2"></a>Exempel 2

`NUMERALSTOTEXT (120, "PL", "", false, 0)` returnerar **"Sto dwadzieścia"**. 

## <a name="example-3"></a>Exempel 3

`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returnerar **"сто двадцать евро 21 евроцент"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
