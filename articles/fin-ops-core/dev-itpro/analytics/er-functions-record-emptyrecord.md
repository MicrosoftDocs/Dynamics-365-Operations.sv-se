---
title: Funktionen EMPTYRECORD ER
description: Det här avsnittet innehåller information om hur funktionen EMPTYRECORD elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/12/2019
ms.topic: article
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
ms.openlocfilehash: e614c06b4cfad628bbd8a966719ed994ce05b792
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746541"
---
# <a name="emptyrecord-er-function"></a>Funktionen EMPTYRECORD ER

[!include [banner](../includes/banner.md)]

`EMPTYRECORD`-funktionen returnerar ett null-värde *behållare (post)* som har samma struktur som den angivna postlistan eller posten.

## <a name="syntax"></a>Syntax

```vb
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]