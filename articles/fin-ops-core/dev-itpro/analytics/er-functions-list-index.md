---
title: INDEX ER-funktionen
description: Den här artikeln innehåller information om hur funktionen INDEX elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 05/20/2021
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
ms.openlocfilehash: 051a2818d862c3bc517e8c20a1742c2599c3bba6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854797"
---
# <a name="index-er-function"></a>INDEX ER-funktionen

[!include [banner](../includes/banner.md)]

`INDEX`-funktionen returnerar värde för *behållare (post)* som väljs med hjälp av det angivna numeriska indexet i den angivna listan. Om indexet är utom räckvidd för posterna i den angivna listan erhålls ett undantag.

## <a name="syntax"></a>Syntax

```vb
INDEX (list, index)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

`index`: *Heltal*

Ett numeriskt index som anger positionen för den önskade posten i den angivna listan.

> [!NOTE]
> Eftersom enbaserad numrering används för den här funktionen måste du ange värdet **1** för att returnera den första posten i den angivna listan.

## <a name="return-values"></a>Returvärden

*Behållare (post)*

Det resulterande postvärdet.

## <a name="example-1"></a>Exempel 1

Om du anger datakällans **DS** för typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `DS.Value` returnera textvärdet **"B"** för den andra posten i denna postlista. Uttrycket `INDEX (SPLIT ("A|B|C", "|"), 2).Value` returnerar också textvärdet **"B"**.

## <a name="example-2"></a>Exempel 2

Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("A|B|C", "|")`, kommer uttrycket `INDEX (SPLIT ("A|B|C", "|"), 4).Value` genererar ett undantag vid körning.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
