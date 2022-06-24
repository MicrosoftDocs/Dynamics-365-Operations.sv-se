---
title: ROUND ER-funktion
description: Den här artikeln innehåller information om hur funktionen ROUND elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 10/21/2020
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
ms.openlocfilehash: 5dce96077ab25f8e545bb99d4bed8fc5bba61e2a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905211"
---
# <a name="round-er-function"></a>ROUND ER-funktion

[!include [banner](../includes/banner.md)]

`ROUND`-funktionen returnerar det specificerade numret som verkligt *värde* efter det avrundats till det angivna antalet decimaler.

## <a name="syntax"></a>Syntax

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a>Argument

`number`: *Realtaltal*

Ett numeriskt värde som måste avrundas.

`decimals`: *Heltal*

Ett numeriskt värde som representerar antalet decimaler.

## <a name="return-values"></a>Returvärden

*Realtal*

Det resulterande numeriska värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Om värdet för `decimals`-argument är större än 0 (noll) avrundas det specificerade numret till det angivna antalet decimaler.

Om värdet för argumentet `decimals` är **0** (noll) avrundas det specificerade numret till närmast jämna heltal.

Om värdet för argumentet `decimals` är mindre än 0 (noll) avrundas det specificerade numret till vänster om decimaltecknet.

## <a name="example-1"></a>Exempel 1

`ROUND (1200.767, 2)` avrundar till två decimaler och returnerar **1200.77**.

## <a name="example-2"></a>Exempel 2

`ROUND (1200.767, -3)` avrundar till närmaste multipel av 1 000 och returnerar **1000**.

## <a name="example-3"></a>Exempel 3

`ROUND (1200.5, 0)` avrundar till närmaste jämna heltal och returnerar **1200**, men `ROUND (1201.5, 0)` returnerar sedan **1202**.

## <a name="additional-resources"></a>Ytterligare resurser

[Matematiska funktioner](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]