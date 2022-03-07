---
title: LIST ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LIST elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: ac8d3971a5502ce567069e0c97247d75a25ae3d38e2cd91e875d4c0d2681d01d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747331"
---
# <a name="list-er-function"></a>LIST ER-funktion

[!include [banner](../includes/banner.md)]

`LIST`-funktionen returnerar ett *postlist*-värde som består av en ny lista med poster som skapas från de angivna argumenten.

## <a name="syntax"></a>Syntax

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a>Argument

`record 1`: *Behållare (post)*

En referens till en datakälla av datatypen *Post*. Detta argument krävs.

`record N`: *Behållare (post)*

En referens till en datakälla av datatypen *Post*. Dessa ytterligare argument är valfria.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Strukturen för listan som skapas innehåller endast de fält som presenteras i strukturen för varje post som nämns i argumenten.

## <a name="example"></a>Exempel

Du anger datakälla **post 1** av typen *behållare*. Den här datakällan innehåller följande kapslade fält av typen *beräknat fält*:

- **Kod:** det här fältet innehåller ett uttryck som returnerar ett värde av typen *Sträng*.
- **Belopp:** det här fältet innehåller ett uttryck som returnerar ett värde av typen *Realtal*.

Du anger datakälla **post 2** av typen *behållare*. Den här datakällan innehåller följande kapslade fält av typen *beräknat fält*:

- **Belopp:** det här fältet innehåller ett uttryck som returnerar ett värde av typen *Realtal*.
- **IsValid:** det här fältet innehåller ett uttryck som returnerar ett värde av typen *Boolesk*.

I det här fallet returnerar uttrycket `LIST('Record 1', 'Record 2')` en ny lista som innehåller två poster. Strukturen för den här listan består av ett enda fält **belopp** av typen *Realtal*, eftersom det här fältet är det enda fält som presenteras i alla argument i den anropade funktionen.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]