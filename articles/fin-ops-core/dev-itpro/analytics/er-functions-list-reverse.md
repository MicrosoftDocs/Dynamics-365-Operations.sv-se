---
title: REVERSE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen REVERSE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 96fc3c2f845f84a5435fd0119a7eaa146caa2dc8da9c931ccfe0915af91ed7cb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752373"
---
# <a name="reverse-er-function"></a>REVERSE ER-funktion

[!include [banner](../includes/banner.md)]

`REVERSE`-funktionen returnerar den angivna listan som ett värde *postlista* i omvänd sorteringsordning.

## <a name="syntax"></a>Syntax

```vb
REVERSE (list)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="example-1"></a>Exempel 1

Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("C|B|A", "|")`, kommer uttrycket `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` att returnera textvärdet **"C"**.

## <a name="example-2"></a>Exempel 2

Om **Leverantör** konfigureras som en ER-datakälla som refererar till tabellen VendTable, kommer uttrycket `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returneras en lista med leverantörerna sorterade efter namn i fallande ordning.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]