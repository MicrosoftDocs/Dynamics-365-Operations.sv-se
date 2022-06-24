---
title: ALLITEMSQUERY ER-funktionen
description: Den här artikeln innehåller information om hur funktionen ALLITEMSQUERY elektronisk rapportering (ER) används.
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
ms.openlocfilehash: f5f8c69e7f67377c2e3d9ccc5a0da1fefe488921
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877166"
---
# <a name="allitemsquery-er-function"></a>ALLITEMSQUERY ER-funktionen

[!include [banner](../includes/banner.md)]

`ALLITEMSQUERY`-funktionen körs som en sammanslagen SQL-fråga. Den returnerar ett nytt tillplattat värde för *postlista* som består av en lista med poster som representerar alla objekt som matchar den angivna sökvägen.

## <a name="syntax"></a>Syntax

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a>Argument

`path`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*. Det måste innehålla minst en relation.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Den angivna sökvägen måste anges som en giltig datakällsökväg för ett datakällselement av datatypen *postlista*. Det måste innehålla minst en relation. Dataelement som sökvägens *sträng* och *datum* bör skapa ett fel i Elektronisk rapportering (ER)-uttrycksgeneratorn vid designtidpunkten.

När den här funktionen används för datakällor av typen *postlista* som refererar till ett programobjekt som kan anropas direkt med hjälp av SQL (till exempel en tabell, entitet eller fråga), körs den som en sammanfogade SQL-fråga. Annars körs i minnet som den [ALLITEMS](er-functions-list-allitems.md)-funktion.

## <a name="example"></a>Exempel

Du definierar följande datakällor i din modellmappning:

- En **CustInv** datakälla av typen *registerposter* som refererar till tabellen CustInvoiceTable
- En **FilteredInv**-datakälla av typen *beräknat fält* som innehåller uttrycket `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`
- En **JourLines** av typen *beräknat fält* som innehåller uttrycket `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`

När du kör en modellmappning att anropa datakällan **JourLines**, kör följande SQL-sats:

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]