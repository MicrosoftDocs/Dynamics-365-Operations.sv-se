---
title: ISVALIDCHARACTERISO7064 ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ISVALIDCHARACTERISO7064 elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: c858ad72db7afe63baca8288f312548c4fc37d5c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041410"
---
# <a name="ISVALIDCHARACTERISO7064">ISVALIDCHARACTERISO7064 ER-funktion</a>

[!include [banner](../includes/banner.md)]

`ISVALIDCHARACTERISO7064`-funktionen returnerar ett *booleskt* värde för **SANT** när en specificerad sträng representerar ett giltigt internationellt bankkontonummer (IBAN). Annars returnerar uttrycket värdet *boolesk* av **FALSK**.

## <a name="syntax"></a>Syntax

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>Argument

`text`: *Sträng*

Ett textvärde som representerar ett IBAN.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="example"></a>Exempel

`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returnerar **"SANT**. 

`ISVALIDCHARACTERISO7064 ("AT61")` returnerar **FALSKT**.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)
