---
title: ALLITEMS ER-funktionen
description: Den här artikeln innehåller information om hur funktionen ALLITEMS elektronisk rapportering (ER) används.
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
ms.openlocfilehash: bb469955c66baf875eea80dde8199986e69e2e71
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274122"
---
# <a name="allitems-er-function"></a>ALLITEMS ER-funktionen

[!include [banner](../includes/banner.md)]

`ALLITEMS`-funktionen körs som ett inbyggt minnesval och returnerar ett nytt utplattat värde för *postlista* som en lista med poster som representerar alla objekt som matchar den angivna sökvägen.

## <a name="syntax"></a>Syntax

```vb
ALLITEMS (path)
```

## <a name="arguments"></a>Argument

`path`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Sökvägen måste anges som en giltig datakällsökväg för ett datakällselement av datatypen *postlista*. Dataelement som sökväg och datum bör skapa ett fel i Elektronisk rapportering (ER)-uttrycksgeneratorn vid designtidpunkten.

Vi rekommenderar inte att du använder den här funktionen för transaktionsdatakällor som kan innehålla en stor mängd data. Överväg i stället att använda funktionen [ALLTEMSQUERY](er-functions-list-allitemsquery.md).

## <a name="example-1"></a>Exempel 1

Om du anger `SPLIT("abcdef" , 2)` som datakälla **DS** returnerar uttrycket `COUNT( ALLITEMS (DS))`**3**.

## <a name="example-2"></a>Exempel 2

Om du anger **Lev** som datakällan för datatypen *Postlista* som refererar till programtabellen VendTable returnerar uttrycket `ALLITEMS (Vend.'<Relations'.ContactPerson)` en förenklad lista med poster som har registerstrukturen **ContactPerson** och innehåller alla kontaktpersoner som kan nås med hjälp **ContactPerson.ContactForParty == VendTable.Party**-relation och som är tillgänglig för alla leverantörer från tabellen refererad leverantör.

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
