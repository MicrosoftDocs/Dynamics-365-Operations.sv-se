---
title: TODAY ER-funktion
description: Den här artikeln innehåller information om hur funktionen TODAY elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/05/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 66797bedd50abace4aab0a2b87b99ad6470233c0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271716"
---
# <a name="today-er-function"></a>TODAY ER-funktion

[!include [banner](../includes/banner.md)]

`TODAY`-funktionen returnerar ett *Datum*-värde som representerar aktuella programmets serverdatum.

## <a name="syntax"></a>Syntax

```xpp
TODAY ()
```

## <a name="return-values"></a>Returvärden

*Datum*

Det resulterande datum-värdet.

## <a name="example"></a>Exempel

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returnerar det aktuella datumet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
