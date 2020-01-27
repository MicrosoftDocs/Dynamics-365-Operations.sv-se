---
title: ROUNDUP ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ROUNDUP elektronisk rapportering (ER) används.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 84a62639b49db17fef1abcda75bc5ad7f08d1005
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917061"
---
# <a name="ROUNDUP">ROUNDUP ER-funktion</a>

[!include [banner](../includes/banner.md)]

`ROUNDUP`-funktionen returnerar det specificerade numret som verkligt *värde* efter det avrundats upp till det angivna antalet decimaler.

## <a name="syntax"></a>Syntax

```
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argument

`number`: *Realtaltal*

Ett numeriskt värde som måste avrundas uppåt.

`decimals`: *Heltal*

Ett numeriskt värde som representerar antalet decimaler.

## <a name="return-values"></a>Returvärden

*Realtal*

Det resulterande numeriska värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Den här funktionen fungerar som [ROUND](er-functions-mathematical-round.md) men avrundar alltid det specificerade numret uppåt (från noll).

## <a name="example-1"></a>Exempel 1

`ROUNDUP (1200.763, 2)` avrundar uppåt till två decimaler och returnerar **1200.77**.

## <a name="example-2"></a>Exempel 2

`ROUNDUP (1200.767, -3)` avrundar uppåt till närmaste multipel av 1 000 och returnerar **2000**.

## <a name="additional-resources"></a>Ytterligare resurser

[Matematiska funktioner](er-functions-category-mathematical.md)
