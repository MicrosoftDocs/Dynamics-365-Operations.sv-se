---
title: Funktionen ENUMERATE ER
description: Den här artikeln innehåller information om hur funktionen ENUMERATE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 2ba0ab6ed3c1625904665d87f56745d9810ac782
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891855"
---
# <a name="enumerate-er-function"></a>Funktionen ENUMERATE ER

[!include [banner](../includes/banner.md)]

`ENUMERATE`-funktionen returnerar ett nytt *postlist*-värde som består av fasta poster i den angivna listan.

## <a name="syntax"></a>Syntax

```vb
ENUMERATE (list)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Listan över fasta poster som returneras exponerar följande ytterligare element:

- Posten av fält (komponenten **Värde**)
- Den aktuella postens index (**Number** component)

## <a name="example"></a>Exempel

I följande illustration har datakällan **Enumerated** skapat en numrerad lista över leverantörsposter från datakällan **Vendors** som refererar till tabellen VendTable.

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

Följande illustration visar flödet av ER-format (elektronisk rapportering). I den här formatlayouten skapas bindningar för att skapa utdata i XML-format. Dessa utdata visar enskilda leverantörer som fasta noder.

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

Följande illustration visar resultatet när det designade formatet har körts.

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]