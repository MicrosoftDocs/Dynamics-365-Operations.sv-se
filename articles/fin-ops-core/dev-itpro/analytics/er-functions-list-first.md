---
title: FIRST ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen FIRST elektronisk rapportering (ER) används.
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
ms.openlocfilehash: d30c8481866ccf3f7080197b37586a0460a4ad2c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746589"
---
# <a name="first-er-function"></a>FIRST ER-funktionen

[!include [banner](../includes/banner.md)]

`FIRST`-funktionen returnerar den första posten i den angivna listan som ett *behållarvärde (post)* om den listan inte är tom. Om listan är tom, genererar den här funktionen ett undantag.

## <a name="syntax"></a>Syntax

```vb
FIRST (list)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

## <a name="return-values"></a>Returvärden

*Behållare (post)*

Det resulterande postvärdet.

## <a name="example-1"></a>Exempel 1

Uttrycket `FIRST(SPLIT("ABC",1)).Value` returnerar textvärdet **"A"**.

## <a name="example-2"></a>Exempel 2

Uttrycket `FIRST(SPLIT("",1)).Value` genererar ett undantag vid körning.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]