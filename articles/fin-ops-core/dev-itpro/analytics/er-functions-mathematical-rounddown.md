---
title: ROUNDDOWN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ROUNDDOWN elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9221476c1c12a7cc3fe2367cdee3ad44e5cbe381
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686892"
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
