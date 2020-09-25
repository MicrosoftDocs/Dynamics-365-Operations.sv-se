---
title: FILTER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen FILTER elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: d281fe710381b0ecb075a0d9281d46bd6edf987d
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745307"
---
# <a name="filter-er-function"></a>FILTER ER-funktion

[!include [banner](../includes/banner.md)]

`FILTER`-funktionen returnerar den angivna listan som ett värde för *postlista* efter att frågan har ändrats så att dess filter enligt det angivna villkoret.

## <a name="syntax"></a>Syntax

```vb
FILTER (list, condition)
```

## <a name="arguments"></a>Argument

`list`: *Post-lista*

Den giltiga sökvägen av en datakälla för datatypen *Postlista*.

`condition`: *Boolesk*

Ett giltigt villkorsuttryck som används för att filtrera poster i den angivna listan.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Till skillnad från funktionen [WHERE](er-functions-list-where.md) tillämpas angivet villkor på alla ER-datakällor (elektronisk rapportering) av typen *Tabellregister* på databasnivå. Listan och villkoret kan definieras med hjälp av tabeller och relationer.

Om ett eller båda argument som har konfigurerats för den här funktionen (`list` och `condition`) inte tillåter att den här begäran översätts till direkt SQL-anrop, genereras ett undantag vid designtillfället. Det här undantaget informerar användaren om att antingen `list` eller `condition` inte kan användas för att fråga databasen.

## <a name="example-1"></a>Exempel 1

Om **Leverantör** konfigureras som en ER-datakälla som refererar till registret VendTable, returnerar uttrycket `FILTER (Vendors, Vendors.VendGroup = "40")` en lista över endast de leverantörer som ingår i leverantörsgrupp 40.

## <a name="example-2"></a>Exempel 2

Om **Leverantör** konfigureras som en ER-datakälla som hänvisar till VendTable-registret och om **parmVendorBankGroup** konfigureras som en ER-datakälla som returnerar ett värde av datatypen *Sträng* returnerar uttrycket `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` returnerar en lista över just de leverantörskonton som tillhör en viss bankgrupp.

## <a name="example-3"></a>Exempel 3

Du anger datakällan **DS** för typen *beräknat fält* som innehåller uttrycket `SPLIT ("A,B,C", ",")`. Du anger sedan ett annat uttryck `FILTER( DS, DS.Value = "B")`. När du försöker spara det här uttrycket i ER formeldesigner, genereras följande undantag: "valideringsfel: listuttrycket för FILTER-funktionen är inte frågningsbar."

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)
