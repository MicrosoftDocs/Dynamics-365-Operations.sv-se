---
title: Funktionen NULLDATE ER
description: Den här artikeln innehåller information om hur funktionen NULLDATE elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 276ad99303a4e88ecb1c83e9518e06bfd7afaa45
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272665"
---
# <a name="nulldate-er-function"></a>Funktionen NULLDATE ER

[!include [banner](../includes/banner.md)]

`NULLDATE`-funktionen returnerar ett *Datum*-värde som representerar **null**-datumet (1 januari 1900).

## <a name="syntax"></a>Syntax

```vb
NULLDATE () as 
```

## <a name="return-values"></a>Returvärden

*Datum*

Det resulterande datum-värdet.

## <a name="example-1"></a>Exempel 1

`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returnerar **null**-datum, 1 januari 1900, som **"1900-01-01"**, baserat på det angivna anpassade formatet.

## <a name="example-2"></a>Exempel 2

Uttrycket `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returnerar **sant** när värdet i fältet **DocumentDate** är lika med **null**-datum. I det här exemplet är **Faktura** är en Elektronisk rapportering (ER) datakälla av typen **Ekonomi/tabellposter** och refererar till tabellen CustInvoiceJour-tabellen.

## <a name="additional-resources"></a>Ytterligare resurser

[Datum- och tidsfunktioner](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
