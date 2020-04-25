---
title: LISTJOIN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LISTJOIN elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249045"
---
# <a name=""></a><a name="LISTJOIN">LISTJOIN ER-funktion</a>

[!include [banner](../includes/banner.md)]

`LISTJOIN`-funktionen returnerar ett *postlist*-värde som representerar av en ny sammanslagen lista med poster som skapas från de angivna argumenten.

## <a name="syntax"></a>Syntax

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a>Argument

`list 1`: *Post-lista*

En referens till en datakälla av datatypen *Postlista*. Det här argumentet är obligatoriskt.

`list N`: *Post-lista*

En referens till en datakälla av datatypen *Postlista*. Dessa ytterligare argument är valfria.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Strukturen för listan som skapas innehåller endast de fält som presenteras i strukturen för varje postlista som nämns i argumenten.

## <a name="example"></a>Exempel

Du anger datakälla **post 1** av typen `Container`. Den här datakällan innehåller följande kapslade fält av typen `Calculated field`:

- **Kod**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `String`.
- **Belopp**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `Real`.

Du anger datakälla **post 2** av typen `Container`. Den här datakällan innehåller följande kapslade fält av typen `Calculated field`:

- **Belopp**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `Real`.
- **IsValid**: det här fältet innehåller ett uttryck som returnerar ett värde av typen `Boolean`.

I det här fallet returnerar uttrycket `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` en ny lista som innehåller två poster. Strukturen för den här listan består av ett enda fält **belopp** av typen `Real`, eftersom det här fältet är det enda fält som presenteras i alla argument i den anropade funktionen.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)
