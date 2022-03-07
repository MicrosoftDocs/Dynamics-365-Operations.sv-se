---
title: SESSIONTODAY ER-funktion
description: Det här avsnittet innehåller information om hur funktionen SESSIONTODAY elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: caadfbe9d82c967b84abd362211a2ecec1bdd0481c7f3907816b7aec23883175
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756487"
---
# <a name="sessiontoday-er-function"></a>SESSIONTODAY ER-funktion

[!include [banner](../includes/banner.md)]

`SESSIONTODAY`-funktionen returnerar ett *Datum*-värde som representerar aktuella programmets sessionsdatum.

## <a name="syntax"></a>Syntax

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a>Returvärden

*Datum*

Det resulterande datum-värdet.

## <a name="example"></a>Exempel

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returnerar det aktuella datumet för programsessionen, 24 december 2015 som strängen **"2015-12-24"**, baserat på den valda tyska kulturen och det angivna formatet.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]