---
title: NULLCONTAINER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NULLCONTAINER elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 13159d9d7c8d1871886beb3cb1938ca8b0097e0efb6f10a9d1b229c49b9ff947
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738586"
---
# <a name="nullcontainer-er-function"></a>NULLCONTAINER ER-funktion

[!include [banner](../includes/banner.md)]

`NULLCONTAINER`-funktionen returnerar ett null-värde *behållare (post)* som har samma struktur som den angivna postlistan eller posten.

## <a name="syntax"></a>Syntax

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a>Argument

`list`: *Postlista* eller *behållare (post)*

Den giltiga sökvägen för en datakälla för antingen typen *Postlista* eller *Behållare (post)*.

## <a name="return-values"></a>Returvärden

*Behållare (post)*

Det resulterande postvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

> [!NOTE] 
> Den här funktionen är föråldrad. Använd `EMPTYRECORD`-funktionen i stället. Mer information finns i [EMPTYRECORD](er-functions-record-emptyrecord.md).

## <a name="example"></a>Exempel

`NULLCONTAINER (SPLIT ("abc", 1))` returnerar en ny tom post som har samma struktur som listan som returneras från `SPLIT`-funktionen. Mer information finns i [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Inspelningsfunktioner](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]