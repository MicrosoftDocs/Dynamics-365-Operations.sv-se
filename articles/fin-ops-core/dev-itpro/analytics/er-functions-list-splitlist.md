---
title: Funktionen SPLITLIST ER
description: Det här avsnittet innehåller information om hur funktionen SPLITLIST elektronisk rapportering (ER) används.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0f527dcf313a6a5e3b6601cac9a0f6495f66833
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680353"
---
# <a name="splitlist-er-function"></a>Funktionen SPLITLIST ER

[!include [banner](../includes/banner.md)]

`SPLITLIST`-funktionen delar upp angivna listan i underlistor (eller batchar) som var och en innehåller det definierade antalet poster. Den returnerar sedan resultatet som ett nytt värde för *postlistan* som består av batchar.

## <a name="syntax"></a>Syntax

```vb
SPLITLIST (list, number)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

`number`: *Heltal*

Det maximala antalet poster per batch.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Listan av batchar som returneras innehåller följande element:

 - **Värde:** *lista*

    Listan över poster som tillhör den aktuella batchen.

- **Batchnumber:** *heltal*

    Numret på den aktuella batchen i den returnerade listan.

## <a name="example"></a>Exempel

Följande bild visar hur en datakälla på en **rad** skapas av tre poster. Den här listan är indelad i batchar som innehåller högst två poster.

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

Följande illustration visar layouten på det designade formatet. I den här formatlayouten skapas bindningar till datakällans **rader** för att skapa utdata i XML-format. Dessa utdata visar enskilda noder för varje batch och poster i den.

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

Följande illustration visar resultatet när det designade formatet har körts.

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)
