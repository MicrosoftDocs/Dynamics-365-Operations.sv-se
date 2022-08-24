---
title: POWER ER-funktion
description: Den här artikeln innehåller information om hur funktionen POWER elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9b6693d7c1afebcf9c30d1bf8d72950053c305bd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274009"
---
# <a name="power-er-function"></a>POWER ER-funktion

[!include [banner](../includes/banner.md)]

`POWER`-funktionen returnerar ett *verkligt* värde som representerar resultatet av att höja det angivna positiva talet till den angivna effekten.

## <a name="syntax"></a>Syntax

```vb
POWER (number, power)
```

## <a name="arguments"></a>Argument

`number`: *Realtal* eller *heltal*

Ett numeriskt värde som måste höjas till den angivna effekten.

`power`: *Realtal* eller *heltal*

Ett numeriskt värde som representerar den specifika effekten.

## <a name="return-values"></a>Returvärden

*Realtal*

Det resulterande numeriska värdet.

## <a name="example-1"></a>Exempel 1

`POWER (10, 2)` returnerar **100**.

## <a name="example-2"></a>Exempel 2

`POWER (4, 0.5)` returnerar **2**.

## <a name="additional-resources"></a>Ytterligare resurser

[Matematiska funktioner](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
