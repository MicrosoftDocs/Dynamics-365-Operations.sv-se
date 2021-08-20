---
title: LISTJOIN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LISTJOIN elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 04/01/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9346afc88adb89c08098f39a5fd1c2cb82f664af2244b8cafbbe8a4d2f516c6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755812"
---
# <a name="listjoin-er-function"></a>LISTJOIN ER-funktion

[!include [banner](../includes/banner.md)]

`LISTJOIN`-funktionen returnerar ett *postlist*-värde som representerar av en ny sammanslagen lista med poster som skapas från de angivna argumenten.

## <a name="syntax"></a>Syntax

```vb
LISTJOIN (list 1 [, list 2, …, list N])
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

![Sidan ER-modellmappningsdesigner.](./media/er-functions-list-listjoin-image1.gif)

I det här fallet returnerar uttrycket `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` en ny lista som innehåller två poster.

![Sidan ER-modellmappningsdesigner med två poster.](./media/er-functions-list-listjoin-image2.gif)

Strukturen för den här listan består av ett enda fält **belopp** av typen `Real`, eftersom det här fältet är det enda fält som presenteras i alla argument i den anropade funktionen.

![Beloppsfält på sidan ER-modellmappningsdesigner.](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)

[Felsöka datakällor i ett kört ER-format för analys av dataflöde och omvandling](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
