---
title: ROUNDAMOUNT ER-funktion
description: Den här artikeln innehåller information om hur funktionen ROUNDAMOUNT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 0e4de43f865ca21822ab2c0c345026d2e9113ca2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286042"
---
# <a name="roundamount-er-function"></a>ROUNDAMOUNT ER-funktion

[!include [banner](../includes/banner.md)]

`ROUNDAMOUNT`-funktionen returnerar ett *verkligt* värde som resultat av avrundning av det angivna numret till närmaste multipel av ett annat tal enligt den angivna avrundningsregeln.

## <a name="syntax"></a>Syntax

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a>Argument

`number`: *Int* eller *Real*

Ett numeriskt värde som måste avrundas.

`decimals`: *Int* eller *Real*

Det tal som `number`-parameterns värde måste avrundas till en multipel av.

`round rule`: *Uppräknat värde*

Ett uppräkningsvärde för den **RoundOffType**-uppräkning som definierar avrundningsregeln. Den här uppräkningen erbjuder följande värden:

- Normal (ordinarie)
- Nedåt (RoundDown)
- Avrundningsmetod (RoundUp)

## <a name="return-values"></a>Returvärden

*Realtal*

Det resulterande numeriska värdet är en multipel av värdet som anges av `decimals`-parametern och är närmast det värde som anges av `number`-parametern.

## <a name="usage-notes"></a>Användningsanteckningar

När `number`-parametern är noll, returnerar den här funktionen alltid noll.

När `decimals`-parametern är noll avrundar den här funktionen till standardvärdet för avrundningsvärden. När `round rule`-parameter är inställd på **RoundOffType.Ordinary** är standardavrundningsvärdet **0.01**. Annars är standardavrundningsvärdet **1.0**.

När `round rule`-parametern är inställd på **RoundOffType.Ordinary** avrundar denna funktion till närmaste avrundningsbelopp.

När `round rule`-parametern är inställd på **RoundOffType.RoundDown** avrundar denna funktion mot noll till närmaste avrundningsbelopp.

När `round rule`-parametern är inställd på **RoundOffType.RoundUp** avrundar denna funktion bort från noll till närmaste avrundningsbelopp.

När `round rule`-parameter är inställd på **RoundOffType.Ordinary**, dden här funktionen uppför sig som [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel-funktion och [ROUND](../dev-ref/xpp-math-run-time-functions.md#round) X++ -funktion.

## <a name="remarks"></a>Kommentarer

Om du vill avrunda ett numeriskt värde till ett angivet antal decimaler använder du funktionen [ROUND](er-functions-mathematical-round.md).

## <a name="example"></a>Exempel

Om parametern **model.RoundOff** är inställd på **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returnerar 7.35. 

Om parametern **model.RoundOff** är inställd på **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returnerar 7.35. 

Om parametern **model.RoundOff** är inställd på **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returnerar 8.4.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)

[Matematiska funktioner](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
