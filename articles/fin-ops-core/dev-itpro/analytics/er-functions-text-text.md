---
title: TEXT ER-funktion
description: Den här artikeln innehåller information om hur funktionen TEXT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: a32da5588c5231b20bc8166d20888c1611ca273e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278869"
---
# <a name="text-er-function"></a>TEXT ER-funktion

[!include [banner](../includes/banner.md)]

Returnera `TEXT`-funktionen det specificerade numret som ett *Sträng*-värde efter att den har konverteras till en textsträng formaterad enligt serverns lokala inställningar för den aktuella programinstansen.

## <a name="syntax"></a>Syntax

```vb
TEXT (number)
```

## <a name="arguments"></a>Argument

`number`: *Heltal* eller *Realtal*

Ett tal som måste konverteras till en textsträng.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

För värden av typen *Realtal* är strängkonverteringen begränsad till två decimaler.

## <a name="example"></a>Exempel

Om serverns lokala inställningar för Microsoft Dynamics 365 Finance-instansen definieras som **EN-US**, `TEXT (NOW ())` returnerar det aktuella Finance sessionsdatumet, 17 december 2015, som textsträng **"12/17/2015 07:59:23 AM"**. `TEXT (1/3)` returnerar **"0.33"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
