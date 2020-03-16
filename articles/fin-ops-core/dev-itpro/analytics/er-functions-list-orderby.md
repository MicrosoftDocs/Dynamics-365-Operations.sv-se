---
title: Funktionen ORDERBY ER
description: Det här avsnittet innehåller information om hur funktionen ORDERBY elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 0a6b5cddc325625dc5b3d677ffcc1da1f8b829cd
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041962"
---
# <a name="ORDERBY">Funktionen ORDERBY ER</a>

[!include [banner](../includes/banner.md)]

`ORDERBY`-funktionen returnerar den angivna listan som ett värde för *postlista* efter att den har sorterats enligt de angivna argumenten. Du kan definiera följande argument som uttryck.

## <a name="syntax"></a>Syntax

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

`expression 1`: *Fält*

Den giltiga sökvägen för ett fält i datakällan som refereras av `list`-argumentet för den anropade funktionen. Det refererade fältet måste vara ett fält av den primitiva datatypen. Detta argument krävs.

`expression N`: *Fält*

Den giltiga sökvägen för ett fält i datakällan som refereras av `list`-argumentet för den anropade funktionen. Det refererade fältet måste vara ett fält av den primitiva datatypen. Dessa ytterligare argument är valfria.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="example-1"></a>Exempel 1

Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("C|B|A", "|")`, kommer uttrycket `FIRST( ORDERBY( DS, DS. Value)).Value` att returnera textvärdet **"A"**.

## <a name="example-2"></a>Exempel 2

Om **Leverantör** konfigureras som en ER-datakälla som refererar till tabellen VendTable, kommer uttrycket `ORDERBY (Vendors, Vendors.'name()')` returneras en lista med leverantörerna sorterade efter namn i stigen ordning.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)
