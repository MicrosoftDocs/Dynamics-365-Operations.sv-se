---
title: Funktionen NUMERALSTOTEXT ER
description: Det här avsnittet innehåller information om hur funktionen NUMERALSTOTEXT elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: e26890a0d99e0df631a3b3350d284e63aaed8e09
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746157"
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