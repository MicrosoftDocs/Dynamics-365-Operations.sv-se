---
title: LISTDISTINCT ER-funktion
description: Den här artikeln innehåller information om hur funktionen LISTDISTINCT elektronisk rapportering (ER) används.
author: kfend
ms.date: 07/30/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: cd773f3455af1be1e952cb3852a648436670ce0f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285288"
---
# <a name="listdistinct-er-function"></a>LISTDISTINCT ER-funktion

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Den här `LISTDISTINCT`-funktionen beräknar det angivna uttrycket som en väljare för varje post i den angivna listan. Det returnerar ett nytt värde för *postlista* som innehåller en enskild post för varje unikt väljarvärde.

## <a name="syntax"></a>Syntax

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

`selector`: *Primitiva datatyp*

Ett giltigt uttryck som används för att beräkna ett väljarvärde för varje post i den angivna listan.

Följande datatyper stöds för den här parametern:

- Booleskt
- Datum
- DatumTid
- GUID
- Heltal
- Int64
- Realtal
- Sträng

## <a name="return-values"></a>Returvärden

*Postlista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Strukturen för listan som skapas matchar strukturen i den angivna listan.

Samma väljarvärde kan beräknas för flera poster i den angivna listan. I det här fallet är fältvärdena för motsvarande post i listan skapad lika med värdena för den första posten från den angivna listan som väljar värdet för.

Det går att utföra den här funktionen på alla datakällor [elektronisk rapportering (ER)](general-electronic-reporting.md) av *postlista* typen som finns i minnet.

Datakällan **GROUPBY** för att generera listan med poster som väljs av en väljare som har distinkta värden. Från ett prestanda- och minnesförbrukningsperspektiv är det emellertid bättre att använda `LISTDISTINCT`-funktionen än **GROUPBY**-datakällan, eftersom körningen av funktionen utförs i minnet.

## <a name="example"></a>Exempel

Följande exempel visar hur du kan få listan med unika kundkontonummer som minst en försäljningsfaktura eller projektfaktura har utfärdats för under en viss period.

1. Ange datakällan **SalesInvoice** för den `Record list`-typ som refererar till **CustInvoiceJour** programregister och filtrerar försäljningsfakturor för specifika perioder.

    `InvoiceAccount`-fältet i den här datakällan returnerar kontonumret för en fakturerad kund.

2. Ange datakällan **ProjectInvoice** för den `Record list`-typ som refererar till **ProjectInvoice** programregister och filtrerar projektfakturor för specifika perioder.

    `InvoiceAccount`-fältet i den här datakällan returnerar kontonumret för en fakturerad kund.

3. Konfigurera datakällan **AllInvoices** som innehåller uttrycket `Calculated field` som innehåller uttrycket `LISTJOIN(SalesInvoice, ProjectInvoice)`.

    Den här datakällan returnerar den kopplade listan över försäljningsfakturor och projektfakturor.

4. Konfigurera datakällan **InvoicedCustomer** som innehåller uttrycket `Record list` som innehåller uttrycket `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.

    Den här datakällan returnerar en ny lista som innehåller en enda post för varje unik kund som har fakturerats under den angivna perioden. `InvoiceAccount`-fältet i den här listan innehåller ett kundkontonummer.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
