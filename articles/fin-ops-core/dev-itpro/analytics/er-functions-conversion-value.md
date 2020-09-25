---
title: VÄRDE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen VALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: ecbffb7e39d7f2f2bccdfe32d593512a65da163c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745523"
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
