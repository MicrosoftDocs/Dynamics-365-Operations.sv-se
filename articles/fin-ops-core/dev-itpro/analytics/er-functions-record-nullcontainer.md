---
title: NULLCONTAINER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NULLCONTAINER elektronisk rapportering (ER) används.
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
ms.openlocfilehash: dac6283ec35d3d03f586ca157048bd3ecc4bfa8a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743937"
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
