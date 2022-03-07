---
title: GUIDVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen GUIDVALUE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 76b918354be9b5b695cfec9d0fe7aca6c5c9e08e01b6e3d0ddfa28af877942e3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733157"
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