---
title: Funktionen ISOCREDREF ER
description: Den här artikeln innehåller information om hur funktionen ISOCREDREF elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/17/2019
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dcbd53ec1939e6fb4bcd829bad01b353e823795a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896775"
---
# <a name="isocredref-er-function"></a>Funktionen ISOCREDREF ER

[!include [banner](../includes/banner.md)]

Funktionen `ISOCREDREF` returnerar ett *Sträng*-värde som representerar en International Organization for Standardization (ISO)-betalningsmottagarreferens baserad på siffror och bokstäver i det angivna fakturanumret.

## <a name="syntax"></a>Syntax

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a>Argument

`invoice number digits`: *Sträng*

Ett textvärde som representerar siffrorna i ett fakturanummer.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

> [!NOTE] 
> Om du vill ta bort symboler som inte överensstämmer med ISO-standarden måste argumentet `invoice number digits` översättas innan den skickas till den här funktionen.

## <a name="example"></a>Exempel

`ISOCredRef ("VEND-200002")` returnerar **"RF23VEND-200002"**.

## <a name="additional-resources"></a>Ytterligare resurser

[Andra (företagsdomänspecifika) funktioner](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]