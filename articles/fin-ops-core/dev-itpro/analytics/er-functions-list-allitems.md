---
title: ALLITEMS ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen ALLITEMS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47113d52e15d3d61f00b3c54229e286eb0f1a8d7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745403"
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
