---
title: Funktionen NULLDATETIME ER
description: Den här artikeln innehåller information om hur funktionen NULLDATETIME elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 3e8447d4f05ee8394842b9b07d14d1c054834bb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867684"
---
# <a name="nulldatetime-er-function"></a>Funktionen NULLDATETIME ER

[!include [banner](../includes/banner.md)]

`NULLDATETIME`-funktionen returnerar ett *DateTime*-värde som representerar **noll** datum/-tid-värdet (1 januari 1900) i Coordinated Universal Time (Greenwich Mean Time \[GMT\]).

## <a name="syntax"></a>Syntax

```vb
NULLDATETIME ()
```

## <a name="return-values"></a>Returvärden

*Datum/tid*

Det resulterande datum/tid-värdet.

## <a name="example"></a>Exempel

`DATETIMEFORMAT( NULLDATETIME(), "O")` returnerar strängvärdet **1900-01-01T00:00:00.0000000+00:00** när det anropas under en process som initierades av en programanvändare som har tidszonsvärde **(GMT) Coordinated Universal Time** i avsnittet **Språk och land/regionpreferenser**.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]