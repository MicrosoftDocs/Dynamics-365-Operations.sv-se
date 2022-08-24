---
title: FILTER ER-funktion
description: Den här artikeln innehåller information om hur funktionen FILTER elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/14/2021
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
ms.openlocfilehash: cfaf76daa8118942c3650e6b39c853434a20ee30
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272601"
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

## <a name="usage-notes"></a><a name="usage-notes"></a>Användningsanteckningar

Till skillnad från funktionen [WHERE](er-functions-list-where.md) tillämpas angivet villkor på alla ER-datakällor (elektronisk rapportering) av typen *Tabellregister* på databasnivå. Listan och villkoret kan definieras med hjälp av tabeller och relationer.

Om ett eller båda argument som har konfigurerats för den här funktionen (`list` och `condition`) inte tillåter att den här begäran översätts till direkt SQL-anrop, genereras ett undantag vid designtillfället. Det här undantaget informerar användaren om att antingen `list` eller `condition` inte kan användas för att fråga databasen.

> [!NOTE]
> Funktionen `FILTER` fungerar på ett annat sätt än funktionen `WHERE` när [`VALUEIN`](er-functions-logical-valuein.md) används för att ange urvalskriterier.
> 
> - Om funktionen `VALUEIN` används inom funktionen `WHERE` område och det andra argumentet för `VALUEIN` gäller en datakälla som inte returnerar några poster, beaktas det booleska värdet *[False](er-formula-supported-data-types-primitive.md#boolean)*-värde som `VALUEIN` returnerar. Därför returnerar uttrycket `WHERE(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` inga leverantörsposter om datakällan **VendGroups** inte returnerar några leverantörsgruppposter.
> - Om funktionen `VALUEIN` används inom funktionen `FILTER` område och det andra argumentet för `VALUEIN` gäller en datakälla som inte returnerar några poster, ignoreras det booleska värdet *[False](er-formula-supported-data-types-primitive.md#boolean)*-värde som `VALUEIN` returnerar. Därför returnerar uttrycket `FILTER(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` alla leverantörsposter som datakällan **Leverantörer** även om datakällan **VendGroups** inte returnerar några leverantörsgruppposter.

## <a name="example-1"></a>Exempel 1

Om **Leverantör** konfigureras som en ER-datakälla som refererar till registret VendTable, returnerar uttrycket `FILTER (Vendors, Vendors.VendGroup = "40")` en lista över endast de leverantörer som ingår i leverantörsgrupp 40.

## <a name="example-2"></a>Exempel 2

Om **Leverantör** konfigureras som en ER-datakälla som hänvisar till VendTable-registret och om **parmVendorBankGroup** konfigureras som en ER-datakälla som returnerar ett värde av datatypen *Sträng* returnerar uttrycket `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` returnerar en lista över just de leverantörskonton som tillhör en viss bankgrupp.

## <a name="example-3"></a>Exempel 3

Du anger datakällan **DS** för typen *beräknat fält* som innehåller uttrycket `SPLIT ("A,B,C", ",")`. Du anger sedan ett annat uttryck `FILTER( DS, DS.Value = "B")`. När du försöker spara det här uttrycket i ER formeldesigner, genereras följande undantag: "valideringsfel: listuttrycket för FILTER-funktionen är inte frågningsbar."

## <a name="additional-resources"></a>Ytterligare resurser

[Lista över funktioner](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
