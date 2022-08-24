---
title: GUIDVALUE ER-funktion
description: Den här artikeln innehåller information om hur funktionen GUIDVALUE elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: cb706a3607b4443c283a91c42c4dc1c389972e44
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285198"
---
# <a name="guidvalue-er-function"></a>GUIDVALUE ER-funktion

[!include [banner](../includes/banner.md)]

`GUIDVALUE`-funktionen konverterar det angivna indata för typen *Sträng* till ett dataobjekt i typen *GUID*.

## <a name="syntax"></a>Syntax

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a>Argument

`input`: *Sträng*

Den giltiga sökvägen till en datakälla av typen *Sträng*.

## <a name="return-values"></a>Returvärden

*GUID*

Det resulterande GUID-värdet (globalt unikt ID).

## <a name="usage-notes"></a>Användningsanteckningar

För att göra en konvertering i motsatt riktning (d.v.s. konvertera angiven indata för datatypen *GUID* till ett dataobjekt i datatypen *sträng*), kan du använda funktionen [TEXT](er-functions-text-text.md).

## <a name="example"></a>Exempel

Du definierar följande datakällor i din modellmappning:

- En **myID**-datakälla av typen *beräknat fält* som innehåller uttrycket `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`
- En **användar** datakälla av typen *registerposter* som refererar till tabellen UserInfo

Du kan sedan använda ett uttryck som `FILTER (Users, Users.objectId = myID)` för att filtrera tabellen UserInfo via fältet **objectId** för datatypen *GUID*.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
