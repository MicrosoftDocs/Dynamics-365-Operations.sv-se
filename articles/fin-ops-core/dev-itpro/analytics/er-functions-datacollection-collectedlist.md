---
title: COLLECTEDLIST ER-funktion
description: Den här artikeln innehåller information om hur funktionen COLLECTEDLIST elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 5102035cf2a8667222beb7bc42ae9aec1b311790
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280907"
---
# <a name="collectedlist-er-function"></a>COLLECTEDLIST ER-funktion

[!include [banner](../includes/banner.md)]

`COLLECTEDLIST`-funktionen ett *postlist*-värde som innehåller listan över värden som returnerades av egenskapen **Collected data key value** för formatelement och samlades in när format elementen användes för att generera utgående dokument under formatkörningen och som uppfyller de angivna villkoren. Varje villkor består av ett nyckelintervall och ett nyckelvärde.

## <a name="syntax"></a>Syntax

```vb
COLLECTEDLIST (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>Argument

`condition 1 range`: *Sträng*

Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för en komponent för elektronisk rapportering (ER)-format. Det här argumentet är obligatoriskt.

`condition 1 value`: *Sträng*

Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key value** för en komponent för ER-format. Det här argumentet är obligatoriskt.

`condition N range`: *Sträng*

Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key name** för en komponent för ER-format. Dessa ytterligare argument är valfria.

`condition N value`: *Sträng*

Ett värde som returneras av uttrycket som har konfigurerats i egenskapen **Collected data key value** för en komponent för ER-format. Dessa ytterligare argument är valfria.

## <a name="return-values"></a>Returvärden

*Post-lista*

Den resulterande listan med poster.

## <a name="usage-notes"></a>Användningsanteckningar

Egenskaperna **Collected data key name** och **Collected data key value** kan konfigureras för antingen en **sekvens**-komponent eller en **XML-element**-komponenten för ett ER-format som finns under **gemensamma\\fil**-komponenten där alternativet **Collect output details** inaktiveras.

Denna funktion returnerar en tom lista när alternativet **Collect output details** på den aktuella komponenten **Allmänt\\Fil** är inaktiverad.

I `condition range`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.

I `condition value`-argumentet kan jokertecknet **"\*"** användas för att representera flera tecken.

## <a name="example"></a>Exempel

För mer information om att använda den här funktionen, se uppgiftsguiden [ER Använd data från formatutmatningen för inventering och summering](tasks/er-format-counting-summing-1.md) (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner.

## <a name="additional-resources"></a>Ytterligare resurser

[Datainsamlingsfunktioner](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
