---
title: Funktionen NULLDATETIME ER
description: Det här avsnittet innehåller information om hur funktionen NULLDATETIME elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 4165f6e064d12200907ac76b6779d35bc578daba
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917498"
---
# <a name="NULLDATETIME">Funktionen NULLDATETIME ER</a>

[!include [banner](../includes/banner.md)]

`NULLDATETIME`-funktionen returnerar ett *DateTime*-värde som representerar **noll** datum/-tid-värdet (1 januari 1900) i Coordinated Universal Time (Greenwich Mean Time \[GMT\]).

## <a name="syntax"></a>Syntax

```
NULLDATETIME ()
```

## <a name="return-values"></a>Returvärden

*Datum/tid*

Det resulterande datum/tid-värdet.

## <a name="example"></a>Exempel

`DATETIMEFORMAT( NULLDATETIME(), "O")` returnerar strängvärdet **1900-01-01T00:00:00.0000000+00:00** när det anropas under en process som initierades av en programanvändare som har tidszonsvärde **(GMT) Coordinated Universal Time** i avsnittet **Språk och land/regionpreferenser**.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)
