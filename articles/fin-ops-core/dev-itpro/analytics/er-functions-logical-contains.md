---
title: CONTAINS ER funktion
description: Det här avsnittet innehåller information om hur funktionen CONTAINS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: 81964681688cebf870bc9b6c59aff0b7fdd82449
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557554"
---
# <a name="contains-er-function"></a>CONTAINS ER funktion

[!include [banner](../includes/banner.md)]

Funktionen `CONTAINS` avgör om den angivna inmatningen innehåller den angivna texten. Det returnerar *booleskt* värde för **SANT** om den angivna inmatningen innehåller den angivna texten. Annars returnerar uttrycket värdet *boolesk* av **FALSK**.

## <a name="syntax"></a>Syntax

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a>Argument

`input`: *Sträng*

Den giltiga sökvägen för en artikel med en datakälla av typen *Sträng* eller en strängkonstant, vilket värdet kan innehålla det andra argumentet.

`search text`: *Sträng*

Den giltiga sökvägen med en datatyp *Sträng* eller en strängkonstant, vilket värdet kan ingå i det första argumentet.

## <a name="return-values"></a>Returvärden

*Booleskt*

Det resulterande *booleska* värdet.

## <a name="usage-notes"></a>Användningsanteckningar

Denna funktion kan användas för att ange ett villkorsuttryck för funktionen [FILTER](er-functions-list-filter.md) function endast när relevant mappning är konfigurerad i [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) för att komma åt [Microsoft Dataverse](../data-entities/data-integration-cds.md). I annat fall är ett undantag genereras på designtid. Det meddelande du får rekommenderar att du använder [WHERE](er-functions-list-where.md)-funktionen i stället för `FILTER`-funktionen.

## <a name="example-1"></a>Exempel 1

Uttrycket `CONTAINS ("abc", "d")` returnerar **FALSE**, medan uttrycket `CONTAINS ("abc", "C")` returnerar **TRUE**.

## <a name="example-2"></a>Exempel 2

Uttrycket `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` returnerar **TRUE** om värdet i fältet **Adress** i datakällan **modell** innehåller strängen **DEU**. Annars returneras **FALSKT**.

## <a name="additional-resources"></a>Ytterligare resurser

[Logiska funktioner](er-functions-category-logical.md)
