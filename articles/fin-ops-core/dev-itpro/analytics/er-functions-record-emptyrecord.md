---
title: Funktionen EMPTYRECORD ER
description: Det här avsnittet innehåller information om hur funktionen EMPTYRECORD elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 1cf23f11fa92adfb7a050efd9c68e80e1bee621f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916900"
---
# <a name="EMPTYRECORD">Funktionen EMPTYRECORD ER</a>

[!include [banner](../includes/banner.md)]

`EMPTYRECORD`-funktionen returnerar ett null-värde *behållare (post)* som har samma struktur som den angivna postlistan eller posten.

## <a name="syntax"></a>Syntax

```
EMPTYRECORD (list)
```

## <a name="arguments"></a>Argument

`list`: *Postlista* eller *behållare (post)*

Den giltiga sökvägen för en datakälla för antingen typen *Postlista* eller *Behållare (post)*.

## <a name="return-values"></a>Returvärden

*Behållare (post)*

Det resulterande postvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

> [!NOTE] 
> En noll post är en post där alla fält innehåller ett tomt värde. Ett tomt värde är **0** (noll) för tal, en tom sträng för strängar, osv.

## <a name="example"></a>Exempel

`EMPTYRECORD (SPLIT ("abc", 1))` returnerar en ny tom post som har samma struktur som listan som returneras från `SPLIT`-funktionen. Mer information finns i [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Inspelningsfunktioner](er-functions-category-record.md)
