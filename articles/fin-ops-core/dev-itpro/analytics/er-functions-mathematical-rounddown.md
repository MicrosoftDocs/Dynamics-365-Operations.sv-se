---
title: ROUNDDOWN ER-funktion
description: Den här artikeln innehåller information om hur funktionen ROUNDDOWN elektronisk rapportering (ER) används.
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
ms.openlocfilehash: e0fa2c92fe63c3c89548b5cc23dd714d3d7589af
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286102"
---
# <a name="rounddown-er-function"></a>ROUNDDOWN ER-funktion

[!include [banner](../includes/banner.md)]

`ROUNDDOWN`-funktionen returnerar det specificerade numret som *verkligt* värde efter det avrundats ned till det angivna antalet decimaler.

## <a name="syntax"></a>Syntax

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argument

`number`: *Realtaltal*

Ett numeriskt värde som måste avrundas nedåt.

`decimals`: *Heltal*

Ett numeriskt värde som representerar antalet decimaler.

## <a name="return-values"></a>Returvärden

*Realtal*

Det resulterande numeriska värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Den här funktionen fungerar som [ROUND](er-functions-mathematical-round.md) men avrundar alltid det specificerade numret nedåt (mot noll).

## <a name="example-1"></a>Exempel 1

`ROUNDDOWN (1200.767, 2)` avrundar nedåt till två decimaler och returnerar **1200.76**. 

## <a name="example-2"></a>Exempel 2

`ROUNDDOWN (1700.767, -3)` avrundar nedåt till närmaste multipel av 1 000 och returnerar **1000**.

## <a name="additional-resources"></a>Ytterligare resurser

[Matematiska funktioner](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
