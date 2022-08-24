---
title: PADLEFT ER-funktion
description: Den här artikeln innehåller information om hur funktionen PADLEFT elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: dac1f9142a381238bf116c4bce65958da8afc4db
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278901"
---
# <a name="padleft-er-function"></a>PADLEFT ER-funktion

[!include [banner](../includes/banner.md)]

`PADLEFT`-funktioner returnerar ett *Sträng*-värde med angiven längd i de fall den aktuella strängens början är utfylld med de angivna tecknen.

## <a name="syntax"></a>Syntax

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett *sträng*-värde som representerar den ursprungliga texten.

`length`: *Heltal*

Ett *heltal*-värde som representerar det sista antalet tecken i den stoppade strängen.

`padding chars`: *Sträng*

De tecken som ska användas för utfyllnad.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`PADLEFT ("1234", 10, "`&nbsp;`")` returnerar textsträngen **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
