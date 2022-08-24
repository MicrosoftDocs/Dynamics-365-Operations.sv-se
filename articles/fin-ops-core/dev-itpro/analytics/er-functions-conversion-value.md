---
title: VÄRDE ER-funktion
description: Den här artikeln innehåller information om hur funktionen VALUE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 0a47637c47ca6c947451efa1230191779401b4e1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277675"
---
# <a name="value-er-function"></a>VÄRDE ER-funktion

[!include [banner](../includes/banner.md)]

`VALUE`-funktionen returnerar ett *verkligt* värde som konverteras från den angivna strängen.

## <a name="syntax"></a>Syntax

```vb
VALUE (text)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett strängvärde som måste konverteras till ett numeriskt värde. 

## <a name="return-values"></a>Returvärden

*Realtal*

Det resulterande numeriska värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Kommatecken och punkter (.) betraktas som decimalavgränsare och ett inledande bindestreck (-) används som ett negativt tecken. Ett undantag genereras vid körning om den specificerade strängen innehåller andra icke-numeriska tecken.

## <a name="example-1"></a>Exempel 1

`VALUE ("1 234,56")` genererar ett undantag.

## <a name="example-2"></a>Exempel 2

`VALUE ("1234,56")` returnerar **1234.56**.

## <a name="additional-resources"></a>Ytterligare resurser

[Funktioner för typkonvertering](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
