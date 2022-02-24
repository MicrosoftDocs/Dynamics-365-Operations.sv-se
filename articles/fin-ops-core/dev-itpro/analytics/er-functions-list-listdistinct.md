---
title: LISTDISTINCT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LISTDISTINCT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 7/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 2333cfc21a16a5905acadd590982020fdf878330
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682277"
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
