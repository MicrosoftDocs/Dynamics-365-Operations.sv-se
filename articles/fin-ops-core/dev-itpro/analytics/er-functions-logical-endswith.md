---
title: ENDSWITH ER-funktionen
description: Den här artikeln innehåller information om hur funktionen ENDSWITH elektronisk rapportering (ER) används.
author: kfend
ms.date: 02/11/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 2608593238e5b2f738b452fb042837238f17e44e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271626"
---
# <a name="endswith-er-function"></a>ENDSWITH ER-funktionen

[!include [banner](../includes/banner.md)]

Funktionen `ENDSWITH` avgör om den angivna inmatningen slutar med den angivna texten. Det returnerar *booleskt* värde för **SANT** om den angivna inmatningen slutar med den angivna texten. Annars returnerar uttrycket värdet *boolesk* av **FALSK**.

## <a name="syntax"></a>Syntax

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a>Argument

`input`: *Sträng*

Den giltiga sökvägen för en artikel med en datakälla av typen *Sträng* eller en strängkonstant, vilket värdet kan sluta med det andra argumentet.

`start text`: *Sträng*

Den giltiga sökvägen med en datatyp *Sträng* eller en strängkonstant, vilket värdet kan ingå i slutet av det första argumentet.

## <a name="return-values"></a>Returvärden

*Booleskt*

Det resulterande *booleska* värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Denna funktion kan användas för att ange ett villkorsuttryck för funktionen [FILTER](er-functions-list-filter.md) function endast när relevant mappning är konfigurerad i [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) för att komma åt [Microsoft Dataverse](/power-platform/admin/data-integrator). I annat fall är ett undantag genereras på designtid. Det meddelande du får rekommenderar att du använder [WHERE](er-functions-list-where.md)-funktionen i stället för `FILTER`-funktionen.

## <a name="example-1"></a>Exempel 1

Uttrycket `ENDSWITH ("abc", "d")` returnerar **FALSE**, medan uttrycket `ENDSWITH ("abc", "C")` returnerar **TRUE**.

## <a name="example-2"></a>Exempel 2

Uttrycket `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` returnerar **TRUE** om värdet i fältet **Adress** i datakällan **modell** slutar med strängen **USA**. Annars returneras **FALSKT**.

## <a name="additional-resources"></a>Ytterligare resurser

[Logiska funktioner](er-functions-category-logical.md)
